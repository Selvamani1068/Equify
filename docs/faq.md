# Frequently Asked Questions {#faq}

## General

**Does Equify replace my telecom provider, or work alongside them?**

Equify works alongside your telecom providers. It does not carry SMS traffic itself — it decides, for every message, which of your registered service providers should carry it, then formats and sends the request on your behalf. You still need at least one active service provider account; Equify is the intelligent layer that sits in front of however many you choose to use.

**What happens if a message doesn't match any of my routing rules?**

It is still delivered. [Round Robin Routing](../routing-setup/round-robin.md) automatically serves as the platform-wide fallback for any traffic that does not match a specific rule, so a message can never be left with no provider to use.

**Can I send messages without connecting a database?**

Yes. Equify supports two integration methods: polling a client database (configured under [Platform Database Setup](../control-centre/database-setup.md)) and a direct HTTPS call to the Message API. Many organizations use both, depending on the application originating the message.

## Dashboard

**Why does a chart on the Dashboard say "No data available"?**

This typically means either no traffic matching that chart's criteria has occurred in the selected period, or — for charts broken down by department, service type, or provider — that the corresponding routing strategy has not yet been configured. For example, **SMS Volume by Department** will show no data until [Functional Routing](../routing-setup/functional-routing.md) has been set up.

**How current is the data shown on the Dashboard?**

Every panel shows its own **Last updated** timestamp. Panels explicitly marked **Live**, such as **Ongoing TPS by Service Provider**, update continuously; others update on a regular interval and can be refreshed manually using the **Refresh** control above the tabs.

## Service Providers and Routing

**Can the same telecom partner be registered more than once?**

Yes, provided each registration uses a different **Channel** — for example, registering the same partner once for SMS and once for WhatsApp — since Equify enforces that a given provider name must be unique per channel.

**What's the difference between deactivating a service provider and removing it from a routing strategy?**

Deactivating a provider (toggling its **Status** off in [Service Provider Management](../control-centre/service-provider-management.md)) stops Equify from sending it any traffic at all, platform-wide. Removing a provider from a single routing strategy's mapping — for example, unchecking it in a [Functional Routing](../routing-setup/functional-routing.md) mapping — only stops it from receiving traffic through that specific rule; it may still receive traffic through other rules or through Round Robin.

**What happens if I don't allocate a full 100% in Percentage Allocation?**

[Percentage Allocation](../routing-setup/percentage-allocation.md) is designed for your configured percentages to add up to 100% across all providers. The **Percentage Distribution Summary** bar at the top of the screen tracks how close you are to fully allocated traffic.

**How many routing strategies can I combine at once?**

There is no fixed limit shown in the application; [Routing Combinations](../routing-setup/routing-combinations.md) lets you add as many of the available strategies to a single execution sequence as your routing logic requires, in any priority order.

## Errors and Retries

**Does Equify retry every failed message automatically?**

Only for error codes you have explicitly enabled retry for, in [Error and Retry Management](../control-centre/error-retry-management.md). Each error code carries its own independent **Enable Retry** setting, so you can choose to retry recoverable errors (such as a timeout) while not retrying unrecoverable ones (such as an invalid recipient number).

**Can different service providers have different error codes and retry policies?**

Yes. Error Management and Retry Management are both configured per service provider, selected from the **Select Service Provider** control at the top of the Error Control Center screen.

## Analytics and Audit

**What's the difference between the Dashboard and the Reports tab in Analytics?**

The [Dashboard](../dashboard/index.md) is built for live, today-focused monitoring and does not require you to set a date range for most of its panels. [Report & Log](../analytics/report-and-log.md) is built for historical, precisely filtered reporting — you choose a date range, optionally narrow by provider, header, department, or template, and generate a downloadable summary, which is the better tool for monthly reviews, vendor performance comparisons, or finance requests.

**How far back can I search the SMS Log?**

The Logs tab under [Report & Log](../analytics/report-and-log.md) explicitly retrieves logs up to two months old. For older history, use the Reports tab, which is not subject to the same limit.

**Who can see what changed in System Audit?**

[System Audit](../administration/system-audit.md) records every configuration change made by every user across the SMS module, and any user with access to the Administration section can search it — there is no per-user restriction shown in the application beyond standard platform access.

## Scope of this guide

**Why is Intelligent Routing marked separately from the rest of Routing Setup?**

Unlike every other chapter in this guide, [Intelligent Routing](../routing-setup/intelligent-routing.md) documents a feature that is confirmed, directly within the application, to not yet be released — it displays its own "Coming Soon" screen with a development timeline and progress indicator. It is documented honestly as a not-yet-available feature rather than described as if it were configurable today.

**Is anything in this guide still missing?**

**Billing**, listed under [Analytics](../analytics/index.md), was visible in the navigation menu during this review but was not opened on screen, so it is not yet documented in detail. Every other screen referenced in the navigation menu — Dashboard, Control Centre, Routing Setup's Traffic Management, Report & Log, and System Audit — has been reviewed and is documented in full in this edition.

---

## Related articles

- [Getting started](Product_Guide/getting_started.md)
- [SMS Overview](overview.md)
- [Whatsapp Overview](overview.md)