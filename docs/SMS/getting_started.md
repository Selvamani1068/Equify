# Getting started

This guide helps you set up and validate SMS messaging in Equify. By the end of this guide, you will:

- Configure system prerequisites  
- Register a service provider  
- Set up routing  
- Send and validate an SMS  

---

## Prerequisites

Before you begin, ensure that:

- The Equify platform is installed *(see [Installation](../Product_Guide/installation.md))*  
- The database is configured *(see [DB Configuration](control-centre/database-setup.md))*  
- At least one SMS provider account is available *(see [Service Provider Registration](control-centre/service-provider-registration.md))*  

---

## Step 1: Configure the database

Set up the database connection required for SMS processing.

1. Go to **Control Centre → Platform DB Setup → DB Configuration**. 
2. Enter the required database details.

For detailed instructions, refer to *[DB Configuration](control-centre/database-setup.md)*.  

You can also:

- Update existing configuration → *[Update DB Configuration](control-centre/update-db-configuration.md)*  
- View saved configuration → *[View DB Configuration](control-centre/view-db-configuration.md)*  

---

## Step 2: Register a service provider

Register an SMS service provider to enable message delivery.

1. Navigate to **Control Centre → Service Provider (SP) → SP Registration**  
2. Add provider details such as credentials and endpoints.

For detailed instructions, refer to *[Register Service Provider](control-centre/service-provider-registration.md)*.

After registration, you can:

- Manage providers → *[Service Provider Management](control-centre/service-provider-management.md)*  
- View provider details → *[View Service Provider Details](control-centre/view-sp-details.md)*  

---

## Step 3: Configure routing strategy

Define how messages are routed to providers.

1. Go to **Routing Setup → Traffic Management**. 
2. Select a routing strategy:
    - *[Round Robin](routing-setup/round-robin.md)*  
    - *[Percentage Allocation](routing-setup/percentage-allocation.md)*  
    - *[Functional Routing](routing-setup/functional-routing.md)*  
    - *[Header Routing](routing-setup/header-routing.md)*  
    - *[Template Routing](routing-setup/template-routing.md)*  
    - *[Service Type Routing](routing-setup/service-type-routing.md)*  
    - *[Geographic Routing](routing-setup/geographic-routing.md)*  
3. Configure rules based on your requirements.

To understand routing concepts, refer to *[Routing Overview](routing-setup/index.md)*.

---

## Step 4: Create routing combinations

Create routing combinations to control message flow.

1. Navigate to **Routing Setup → Routing Management → Combinations**.  
2. Define routing logic using configured service providers.

For detailed instructions, refer to *[Create Routing Combinations](routing-setup/routing-combinations.md)*.

You can also:

- Modify combinations → [Edit Routing Combinations](routing-setup/edit_routing_combination.md)  

---

## Step 5: Send a test SMS

Validate your configuration by sending a test message.


1. Trigger an SMS request (via database or API).  
2. Verify message delivery status in *[Reports and Logs](analytics/report-and-log.md) *.   

If messages fail:

- Check retry handling → [Error Control Center](control-centre/error-retry-management.md)  
- Verify routing → [Routing Overview](routing-setup/index.md)  

---

## Step 6: Monitor message delivery

Track delivery status and system logs.

1. Navigate to **Analytics → Reports & Logs**  
2. Review:
    - Delivery status  
    - Errors  
    - Retry attempts  

For detailed insights, refer to *[Reports and Logs](analytics/report-and-log.md)*.  

For auditing, refer to *[System Audit](administration/system-audit.md)*.

---

## Related articles

- [DB Configuration](control-centre/database-setup.md)  
- [Service Provider Registration](control-centre/service-provider-registration.md)  
- [Routing Setup](routing-setup/index.md)  
- [Reports and Logs](analytics/report-and-log.md)  


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