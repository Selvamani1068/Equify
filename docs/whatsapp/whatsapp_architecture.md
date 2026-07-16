# Architecture

---

This chapter describes the technical architecture of the Equify WhatsApp platform and explains how its core components interact to process, deliver, track, and monitor WhatsApp communications.

At a high level, the Equify WhatsApp architecture consists of three logical domains:

| Domain | Description |
|------------|-------------|
| Client System | Submit WhatsApp communication requests through APIs and receives delivery status updates |
| Equify Platform | Processes, delivers, tracks, and monitors WhatsApp communications |
| Service Providers | Deliver messages to end recipients |

## Equify platform architecture

  ![SMS Architecture](../../assets/images/whatsapp_arch.svg)

---

## Architectural domains

### Client system

The Client System represents the business applications that generate WhatsApp communication requests and consume delivery status information.

Unlike Equify SMS, which supports both API-based and database-driven message submission, Equify WhatsApp supports communication requests exclusively through APIs.

The client environment may include:

- Identity Provider (IDP) for user authentication
- Enterprise applications
- Banking platforms
- Customer engagement applications
- Marketing automation systems
- Output databases that receive message delivery status information

Authentication is handled via SSO using OIDC with an external Identity Provider.

Enterprise applications invoke Equify APIs to initiate WhatsApp communications. Delivery status information can be written back to configured output databases for downstream processing and reporting.

### Equify platform

The Equify Platform is responsible for communication orchestration and contains three major processing engines:

- Message Processing Engine
- DLR Processing Engine
- Analytics Engine

These engines collectively manage message delivery, delivery report processing, monitoring, analytics, and operational governance.

### Service providers

Service Providers are external messaging providers responsible for delivering communications to end recipients.

Equify integrates with multiple providers through a unified framework and abstracts provider-specific implementations from enterprise applications. This enables centralized provider management, template administration, message delivery, and status tracking.

---

## Message processing engine

The Message Processing Engine is responsible for receiving, validating, processing, and dispatching messages.

### Message API service

The Message API Service acts as the entry point into the platform.

- Exposes secure HTTPS APIs for message submission
- Validates incoming requests
- Transforms requests into a standardized internal format
- Publishes structured messages to Kafka in encrypted form

All communication into the platform is API-driven.

### Operations and maintenance service

The Operations and Maintenance Service provides administrative capabilities for managing the platform configuration.

Administrators use this service to manage provider configurations, Template definitions, Category mappings, and integration settings. The service also supplies configuration data required by runtime services and supports dashboard and analytics functions.

Configuration data is persisted in MySQL and synchronized to Redis to support low-latency access by processing services.

### Kafka cluster

Kafka is used to exchange message requests, delivery events, audit records, and operational metrics between platform services. This asynchronous architecture enables scalable and fault-tolerant message processing across the platform.

### Middleware service

The Middleware Service performs business-rule validation and template validation.

The service:

- Validates incoming requests
- Verifies that the submitted template is registered for the selected provider
- Validates template categories
- Performs business-rule enforcement
- Prepares messages for delivery processing
- Routes messages to provider-specific Kafka topics based on configuration

Before a message is dispatched, the Middleware Service validates that the submitted template identifier exists and is registered for the target service provider. Requests containing unregistered templates are rejected before delivery processing begins.

### Template management service

The Template Management Service manages provider-approved WhatsApp templates used for communication delivery.

When a template is added in Equify, the platform captures:

- Template identifier
- Template definition
- Associated service provider
- Template category
- Approval status

Supported WhatsApp categories include:

- Authentication
- Utility
- Marketing

Template registration enables Equify to classify message traffic by category and generate category-based analytics, usage reporting, and billing information.

Template information is made available to runtime services for validation and processing.

### Dispatcher service

The Dispatcher Service consumes validated communication requests and transforms them into provider-specific formats.

The service invokes the provider's HTTPS APIs and submits the message for delivery.

### Redis cache

Redis is used as a high-performance in-memory data store for runtime processing.

It stores:

- Configuration data (synced from MySQL)
- Template and provider metadata
- Message correlation data (Message ID & Provider ID mapping)

This enables fast lookup for DLR processing and message tracking.

---

## DLR processing layer

The DLR Processing Layer manages message lifecycle updates received from WhatsApp service providers.

### DLR API service

Service providers send message status updates back to Equify through dedicated HTTPS API endpoints.

These reports contain status information that indicates whether messages were delivered successfully, DLR, read, MO, CTA, or encountered processing error.

Received status payloads are validated and published to Kafka for processing.

### DLR processor service

The DLR Processor consumes status events from Kafka.

The service:

- Retrieves the corresponding message identifier from Redis.
- Correlates the provider response with the original message request.
- Consolidates message lifecycle information.
- Updates the configured output destination.

Depending on configuration, delivery status information can be:

- Updated in the client output database
- Written to CSV files for downstream processing

---

## Analytics and operations layer

The Analytics and Operations Layer provides visibility into communication activity, platform performance, and infrastructure health.

It transforms messaging events, delivery information, audit logs, and operational metrics into dashboards, reports, alerts, and monitoring insights that support day-to-day operations and platform administration.

### ClickHouse analytics store

Communication events, delivery information, audit logs, and operational metrics are processed through the analytics pipeline and stored in ClickHouse for reporting and analysis.

The platform stores:

- Communication activity
- Delivery statistics
- Template category information
- Category-wise message volumes
- Provider-wise usage statistics
- Audit logs
- System health metrics
- Application performance metrics

### Redis cache

Redis is used as the platform's in-memory data store for runtime processing.

Frequently accessed configuration data, template information, provider configurations, and message correlation data are maintained in Redis to support low-latency processing across platform services.

### System metrics collection

Background monitoring scripts execute periodically across all servers and collect metrics related to:

- CPU utilization
- Memory utilization
- Network health
- Kafka status
- Redis status
- Database status
- Application availability

The collected data is published to Kafka and processed by ClickHouse for reporting purposes.

### Analytics processing

Communication events, delivery information, audit records, and system metrics are processed through the analytics engine and prepared for reporting and operational analysis.

### Dashboard and reporting services

In addition to communication metrics, Equify provides visibility into platform and infrastructure health. Operations teams can monitor resource utilization, service availability, messaging infrastructure status, and database health from a centralized monitoring interface.

Reporting capabilities help organizations analyze:

- Message volumes
- Delivery trends
- Provider performance
- Failure Rate
- Operational activity
- Audit information
- Infrastructure utilization
- Service availability and platform health

These dashboards help operations teams monitor communication activity, investigate delivery issues, and evaluate provider performance.

---

## End-to-end communication flow

The following sequence summarizes the complete communication lifecycle:

1. A business application generates a WhatsApp communication request via API.
2. The Message API Service validates and transforms the request.
3. The request is encrypted and published to Kafka.
4. The Middleware Service validates business rules and routes the message to a provider-specific topic.
5. The template category (Authentication, Utility, or Marketing) is identified and associated with the message for reporting and billing purposes.
6. The Dispatcher Service consumes the message, transforms it, and sends it to the provider via HTTPS.
7. The service provider delivers the message to the recipient.
8. The provider sends delivery reports (DLR) back to Equify via HTTPS callbacks.
9. Final delivery results are written to the configured output destination.
10. Audit logs and system metrics are published to Kafka.
11. The Analytics Engine processes events and stores them in ClickHouse.
12. Dashboards and reports provide operational and analytical insights.

---

## What to do next

- Set up the system using [Getting started](../SMS/getting_started.md)
- Configure components in [Control centre](control-centre/index.md)
- Add template in [Routing setup](routing-setup/index.md)

<div class="home-support-banner">
  <div class="support-left">
    <h2 class="support-title">Need some help?</h2>
    <p class="support-desc">
      Communication at scale isn’t always simple. Get instant help from our
      <a href="/support/">support team</a>, or browse the
      <a href="/faq/#faq">FAQ</a> for quick answers.
    </p>
    <div class="support-legal">
      <a href="/terms/">Terms of service</a>
      <a href="/privacy/">Privacy Policy</a>
      <span>© 2026 Equify. All rights reserved.</span>
    </div>
  </div>
  <div class="support-right">
    <div class="support-icon-cluster">
      <div class="support-icon-bubble support-icon-bubble--1">🎧</div>
      <div class="support-icon-bubble support-icon-bubble--2">💬</div>
      <div class="support-icon-bubble support-icon-bubble--3">🛡️</div>
    </div>
  </div>
</div>
