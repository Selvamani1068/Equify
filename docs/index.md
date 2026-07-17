---
hide:
  - toc
---
<div class="home-page">
<div class="home-hero">

<div class="hero-content">

<h1 class="hero-title">Communication Orchestration Platform</h1>

<p class="hero-description">
Equify centralizes communication processing, provider management,<br>
routing, monitoring, analytics, and governance for SMS and WhatsApp<br>
communications at scale.
</p>

<div class="hero-buttons">

<a href="#get-started" class="hero-btn">
<strong>Get Started →</strong>
</a>

<a href="#sms-modules" class="hero-btn">
<strong>SMS Module →</strong>
</a>

<a href="#whatsapp-modules" class="hero-btn">
<strong>Whatsapp Module →</strong>
</a>
</div>

<div class="release-info">
Version 5.2.1 • Released 30 June 2026 •
<a href="release_notes/">Release Notes</a>
</div>

</div>

<div class="hero-image">
<img src="assets/images/home-logo.png" alt="SMS Hero">
</div>
<hr class="hero-divider">
</div>
<div id="get-started" class="home-title">
Get started
</div>
<div class="home-subtext">
Start building scalable, intelligent SMS workflows in minutes.
</div>
<div class="quickstart-grid">

<div class="quick-card">

<div class="quick-content">

<h3>About Equify</h3>

<p>
Learn how Equify manages communication processing, routing, delivery tracking, and operational monitoring.
</p>

<a href="Product_Guide/overview1/#introduction" class="card-link">
Explore Overview →
</a>

</div>
</div>

<div class="quick-card">

<div class="quick-content">

<h3>Installation & Setup</h3>

<p>
Set up Equify and prepare the platform for enterprise messaging operations.
</p>

<a href="Product_Guide/installation/#introduction" class="card-link">
Start Setup →
</a>

</div>
</div>

</div>

<hr class="hero-divider1">

<div id="sms-modules" class="home-title1">
SMS Modules
</div>
<div class="home-subdesc">
Find everything you need to build, manage, and scale your SMS experience.
</div>

<div class="card-actions">
<a href="SMS/analytics/#analytics" class="card-btn">
<strong>View Analytics →</strong>
</a>

<a href="SMS/administration/#admin" class="card-btn">
<strong>Administration →</strong>
</a>

</div>

<div class="quickstart-grid">

<div class="quick-card">

<div class="quick-content">

<h3>Dashboard</h3>

<p>
Monitor messaging activity, delivery performance, failures, retries, and platform health.
</p>

<a href="SMS/dashboard/dashboard_index/#dashboard" class="explore-link">
Open Dashboard →
</a>
</div>
</div>

<div class="quick-card">

<div class="quick-content">

<h3>Control Centre</h3>

<p>
Manage databases, providers, configurations, and operational settings from a centralized console.
</p>

<a href="SMS/control-centre/#control_centre" class="explore-link">
Manage Platform →
</a>

</div>
</div>
<div class="quick-card">

<div class="quick-content">

<h3>Routing Setup</h3>

<p>
Configure intelligent routing strategies using provider allocation, headers, templates, geography, service type, and failover rules.
</p>

<a href="SMS/routing-setup/#routing" class="explore-link">
Configure Routing →
</a>

</div>
</div>
</div>


<hr class="hero-divider1">

<div id="whatsapp-modules" class="home-title1">
Whatsapp Modules
</div>
<div class="home-subdesc">
Find everything you need to build, manage, and scale your WhatsApp experience.
</div>


<div class="card-actions">
<a href="whatsapp/analytics/#analytics" class="card-btn">
<strong>View Analytics →</strong>
</a>

<a href="whatsapp/administration/#admin" class="card-btn">
<strong>Administration →</strong>
</a>

</div>

<div class="quickstart-grid">

<div class="quick-card">

<div class="quick-content">

<h3>Dashboard</h3>

<p>
Monitor messaging activity, delivery performance, failures, retries, and platform health.
</p>

<a href="whatsapp/dashboard/dashboard_index/#dashboard" class="explore-link">
Open Dashboard →
</a>
</div>
</div>

<div class="quick-card">

<div class="quick-content">

<h3>Control Centre</h3>

<p>
Manage databases, providers, configurations, and operational settings from a centralized console.
</p>

<a href="whatsapp/control-centre/#control_centre" class="explore-link">
Manage Platform →
</a>

</div>
</div>
<div class="quick-card">

<div class="quick-content">

<h3>Template Management</h3>

<p>
Register and manage provider-approved WhatsApp templates used for business communications.
</p>

<a href="whatsapp/template-management/#template_management" class="explore-link">
Manage Templates →
</a>

</div>
</div>
</div>

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
<script>
document.addEventListener("DOMContentLoaded", function () {

  function injectSidebarLinks() {

    const sidebarInner = document.querySelector(".md-sidebar--primary .md-sidebar__inner");
    const tabs = document.querySelectorAll(".md-tabs__link");

    if (!sidebarInner || !tabs.length) return;

    // prevent duplicate
    if (document.querySelector(".custom-shortcuts")) return;

    // Create container (SAFE – not touching nav list)
    const container = document.createElement("div");
    container.className = "custom-shortcuts";

    tabs.forEach(tab => {
      const text = tab.textContent.trim();
      if (text === "Home") return;

      const link = document.createElement("a");
      link.href = tab.href;
      link.className = "shortcut-link";
      link.textContent = text;

      container.appendChild(link);
    });

    // Insert ABOVE navigation (safe)
const title = sidebarInner.querySelector(".md-nav__title");

if (title) {
  title.insertAdjacentElement("afterend", container);
} else {
  sidebarInner.prepend(container);
}
  }

  injectSidebarLinks();
  document.addEventListener("pjax:end", injectSidebarLinks);

});
</script>

