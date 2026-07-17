# Overview

---

Equify WhatsApp enables organizations to send and manage business communications over WhatsApp through API-based integrations with supported telecom service providers.

The platform provides a centralized framework for managing WhatsApp Business messaging operations, including provider integration, template management, message delivery tracking, operational monitoring, auditability, and reporting.

Unlike traditional messaging systems that require separate management for each provider, Equify simplifies WhatsApp communication operations through a unified administration experience while maintaining visibility and control across the entire messaging lifecycle.

Key platform differentiators include:

- Support for multiple WhatsApp-enabled telecom service providers through a unified integration framework
- Centralized registration and management of provider-approved WhatsApp templates
- Template-based category tracking for analytics, usage monitoring, and billing
- Support for WhatsApp template categories, including Authentication, Utility, and Marketing messages
- Real-time message delivery tracking and status monitoring
- Centralized audit logging and operational reporting
- Unified administration and provider management experience

By centralizing WhatsApp communication operations, Equify helps organizations streamline customer engagement, improve operational efficiency, maintain regulatory compliance, and gain complete visibility into message delivery and performance.

---

## Key features

Equify provides the following capabilities to support large-scale WhatsApp communication operations:

- **Dashboard and monitoring** – Monitor messaging activity, delivery performance, and platform health from a centralized dashboard.
- **Communication processing** – Receive and process WhatsApp communication requests submitted through Equify APIs.
- **Multi-provider management** – Integrate and manage multiple WhatsApp service providers through a unified interface.
- **Template management** – Register and manage provider-approved WhatsApp templates and capture associated message categories for communication tracking and reporting.
- **Category-based classification** – Track and classify WhatsApp communications as Authentication, Utility, or Marketing messages for operational reporting, analytics, and billing.
- **Message delivery tracking** – Track message status and delivery outcomes throughout the communication lifecycle.
- **Analytics and reporting** – Analyze communication performance through operational reports and dashboards.
- **Audit and governance** – Maintain visibility into configuration changes, template updates, and administrative activities.
- **Centralized administration** – Manage platform settings, provider configurations, templates, and user access from a single location.

---

## How Equify works

Equify manages the complete lifecycle of WhatsApp business communications through a centralized orchestration framework.

1. Enterprise applications submit WhatsApp communication requests through APIs.
2. Equify validates and processes incoming message requests.
3. Equify validates that the submitted template is registered for the selected service provider.
4. The associated template category (Authentication, Utility, or Marketing) is identified and applied for message processing, analytics, and billing purposes.
5. Messages are transformed into provider-specific formats and submitted to the configured WhatsApp service provider.
6. Providers process and deliver messages through the WhatsApp Business platform.
7. Delivery acknowledgments and status updates are collected and processed.
8. Message status information and template category data are stored for tracking, analytics, usage reporting, billing, and auditing.
9. Operational metrics are generated and presented through dashboards and analytics.

This workflow enables organizations to manage WhatsApp communications efficiently while maintaining operational visibility, governance, and delivery tracking across the messaging ecosystem.

!!! note
    Equify WhatsApp supports only API-based message submission. Unlike Equify SMS, inbound database integrations are not supported for WhatsApp communication requests.
    
---

## What to do next

- Understand system design in [Architecture](whatsapp_architecture.md)
- Set up the system using [Getting started](getting_started.md)
- Monitor activity in [Dashboard](dashboard/dashboard_index.md)

<div class="home-support-banner">
  <div class="support-left">
    <h2 class="support-title">Need some help?</h2>
    <p class="support-desc">
      Communication at scale isn’t always simple. Get instant help from our
      <a href="info@equence.com">support team</a>, or browse the
      <a href="/faq/#faq">FAQ</a> for quick answers.
    </p>
    <div class="support-legal">
      <a href="https://equence.com/terms.html">Terms of service</a>
      <a href="https://equence.com/privacy-policy.html">Privacy Policy</a>
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