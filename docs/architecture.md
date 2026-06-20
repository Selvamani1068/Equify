## Architecture Overview

Equify follows a distributed, event-driven architecture designed to support high-volume SMS communication processing across multiple telecom service providers.

The platform acts as an intermediary layer between enterprise systems and external messaging networks. It separates message generation from message delivery, allowing organizations to manage communication policies, provider integrations, routing rules, delivery tracking, and operational reporting through a centralized platform.

The architecture is designed to provide:

- Scalability for high-volume messaging workloads
- Provider-independent communication management
- Configurable routing and delivery control
- Reliable message processing and delivery tracking
- Operational visibility and monitoring
- Centralized administration and governance
---

## Architectural Components

The Equify platform consists of several logical layers that work together to process and manage SMS communications.

### Integration Layer

The Integration Layer serves as the entry point for communication requests.

Equify supports both application-driven and database-driven integration models. Enterprise applications can submit SMS requests through APIs, while organizations that rely on database-based workflows can integrate directly through database connectors.

### Message Processing Layer

The Message Processing Layer validates incoming requests and prepares them for delivery.

During this stage, Equify applies communication policies, evaluates routing requirements, and prepares messages for downstream processing. This layer ensures that all requests are processed consistently regardless of the originating system or delivery provider.

### Routing and Delivery Layer

The Routing and Delivery Layer is responsible for provider selection and message dispatch.

Based on configured routing policies, Equify determines the most appropriate provider for each message. Routing decisions can be influenced by message attributes, departments, templates, headers, service types, or traffic distribution requirements.

After a provider is selected, Equify transforms the request into the format required by the destination provider and initiates message delivery.

### Delivery Tracking Layer

The Delivery Tracking Layer manages message status updates throughout the communication lifecycle.

Delivery acknowledgments and delivery reports received from telecom providers are processed and correlated with the original message request. This enables organizations to track message progress from submission through final delivery.

### Analytics and Monitoring Layer

The Analytics and Monitoring Layer provides operational visibility across the platform.

This layer collects communication metrics, delivery statistics, provider performance data, and system health information. The collected data is used to generate dashboards, reports, and operational insights that support monitoring and decision-making activities.

### Administration Layer

The Administration Layer provides centralized configuration and governance capabilities.

Administrators can manage provider configurations, routing policies, retry settings, user access, communication rules, and platform-wide settings through a unified interface.

Audit capabilities provide visibility into configuration changes and administrative activities across the platform.

---

## Message Processing Flow

A message enters Equify through one of two integration methods:

API Integration through the Message API Service
Database Integration through the DB Connector Service

For database-driven integrations, Equify can retrieve records directly from client databases or process change events through Debezium-based Change Data Capture (CDC).

After receiving a message request, Equify publishes the message to a Kafka-based processing pipeline. Kafka acts as the platform's event-streaming backbone and enables reliable message processing across multiple platform services.

The message lifecycle consists of the following stages:

1. A business application or database submits an SMS request.
2. The Message Processing Engine validates the incoming request.
3. The message is published to Kafka topics for downstream processing.
4. The Middleware Service applies routing and processing policies.
5. The Dispatcher Service transforms the message into the format required by the selected provider.
6. The message is transmitted to the telecom service provider through secure HTTPS interfaces.
7. The Retry Service monitors provider responses and automatically reroutes failed requests according to configured retry policies.
8. Delivery reports (DLRs) are received through the DLR API.
9. The DLR Processor correlates delivery responses with the original message and updates message status information.
10. Delivery status information is written to the configured output database.
11. Operational metrics, logs, and audit events are collected and processed for reporting and monitoring purposes.
