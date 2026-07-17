# Getting started

This guide helps you set up and validate WhatsApp messaging in Equify. By the end of this guide, you will:

- Configure system prerequisites  
- Register a service provider  
- Create WhatsApp templates
- Send and validate a WhatsApp message
- Monitor message delivery and status updates 

---

## Prerequisites

Before you begin, ensure that:

- The Equify platform is installed *(see [Installation](../Product_Guide/installation.md))*  
- The database is configured *(see [DB configuration](control-centre/database-setup.md))*  
- At least one SMS provider account is available *(see [Service provider registration](control-centre/service-provider-registration.md))*  

---

## Step 1: Configure the database

Set up the database connection required for WhatsApp processing.

1. Go to **Control Centre → Platform DB Setup → DB Configuration**. 
2. Enter the required database details.

For detailed instructions, refer to *[DB configuration](control-centre/database-setup.md)*.  

You can also:

- Update existing configuration → *[Update DB configuration](control-centre/update-db-configuration.md)*  
- View saved configuration → *[View DB configuration](control-centre/view-db-configuration.md)*  

---

## Step 2: Register a service provider

Register an WhatsApp service provider to enable message delivery.

1. Navigate to **Control Centre → Service Provider (SP) → SP Registration**  
2. Add provider details such as credentials and endpoints.

For detailed instructions, refer to *[Register service provider](control-centre/service-provider-registration.md)*.

After registration, you can:

- Manage providers → *[Service provider management](control-centre/service-provider-management.md)*  
- View provider details → *[View service provider details](control-centre/view-sp-details.md)*  

---

## Step 3: Add WhatsApp templates

Before messages can be sent, provider-approved WhatsApp templates must be registered in Equify.

During registration, Equify captures the template category associated with the approved template. This information is later used for message classification, analytics, usage tracking, and billing.

1. Go to **Template Management → Add Template**.
2. Create a new template.
3. Specify the category assigned by the WhatsApp provider:
    - Authentication
    - Utility
    - Marketing

For detailed instructions, refer to *[Add template](template-management/add-template.md)*.

After template creation, you can:

- Edit templates → *[Edit Template](template-management/edit_template.md)*
- Delete templates → *[Delete Template](template-management/delete_template.md)*

!!! note
    Every WhatsApp message submitted through Equify must reference a template that has been registered for the selected service provider. During message processing, Equify validates the template-to-provider mapping before forwarding the request to the provider.

---

## Step 4: Send a test WhatsApp message

Validate your configuration by sending a test WhatsApp message.


1. Submit a WhatsApp message request using the Message API.
2. Specify a template that is registered for the selected service provider.
3. Submit the request.
4. Verify message delivery status in *[Reports and logs](analytics/report-and-log.md) *.   

---

## Step 5: Monitor message delivery

Track delivery status and system logs.

1. Navigate to **Analytics → Reports & Logs**  
2. Review:
    - Delivery status  
    - Errors  

For detailed insights, refer to *[Reports and logs](analytics/report-and-log.md)*.  

For auditing, refer to *[System audit](administration/system-audit.md)*.

---

## Related articles

- [DB configuration](control-centre/database-setup.md)  
- [Service provider registration](control-centre/service-provider-registration.md)  
- [Template management](template-management/index.md)  
- [Reports and logs](analytics/report-and-log.md)  

<div class="home-support-banner">
  <div class="support-left">
    <h2 class="support-title">Need some help?</h2>
    <p class="support-desc">
      Communication at scale isn’t always simple. Get instant help from our
      <a href="https://equence.com/contact.html">support team</a>, or browse the
      <a href="../faq/#faq">FAQ</a> for quick answers.
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