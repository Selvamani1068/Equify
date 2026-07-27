# Installation {#installation}

---

Perform the following steps to install Equify.

---

### Prepare the environment

1. Verify that all system requirements are met.
2. Ensure that the following services are installed and running:
    - Kafka
    - Redis
    - MySQL
    - ClickHouse
    - Vault
    - Nginx

---

### Deploy the application

1. Upload the Equify application packages (JAR files) to the target servers using FTP.
2. Place the application files in the appropriate directories.
3. Configure environment variables and application properties.

---

### Configure components

1. Configure database connections.
2. Configure Kafka brokers and topics.
3. Configure Redis and Vault integration.
4. Configure Nginx as a reverse proxy.

---

### Start services

1. Start backend services.
2. Start database connectors and API services.
3. Start webhook and DLR processing services.
4. Start the UI services.

---

### Verify installation

1. Verify that all services are running.
2. Check logs for errors.
3. Verify that application endpoints are accessible.

---

## What to do next

- Complete initial setup in [Getting started](getting_started.md)
- Explore SMS capabilities in [SMS Overview](../overview.md)

<div class="home-support-banner">
  <div class="support-left">
    <h2 class="support-title">Need some help?</h2>
    <p class="support-desc">
      Communication at scale isn’t always simple. Get instant help from our
      <a href="https://equence.com/contact.html">support team</a>, or browse the
      <a href="../../faq/#faq">FAQ</a> for quick answers.
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