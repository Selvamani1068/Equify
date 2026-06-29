# Report & Log

**Report & Log** is where Equify's traffic history becomes something you can filter precisely, export, and hand to someone outside the platform — a compliance team, a finance partner, or a customer support agent investigating a single complaint.

## Opening Report & Log

In the left-hand navigation menu, select **Analytics › Report & Log**. The screen opens with two tabs in the top-right corner: **REPORTS** and **LOGS**.

## The Reports tab

The **Reports** tab generates aggregated, summary-level reports — *"View reports across service providers, headers and departments"* — and is the tab selected by default.

### Filtering a report

The **Reports Filter** panel lets you narrow a report before generating it:

| Field | Description |
|---|---|
| **Service Provider** | Restrict the report to one or more specific providers, or leave as **All Service Provider** |
| **Header** | Restrict the report to traffic carrying a specific [header](../routing-setup/header-routing.md), or leave as **All Header** |
| **Department** | Restrict the report to a specific [department](../routing-setup/functional-routing.md), selected from a checklist that includes **Select All** alongside each individually configured department (CREDIT, LOAN, INSURANCE, HR, SALES, FINANCE, and others) |
| **Template IDs** | Restrict the report to one or more specific [template](../routing-setup/template-routing.md) IDs, entered directly (for example `123, 456…`) |
| **Date Range** *(required)* | The period the report should cover, using the same calendar control used throughout Equify, with quick-select options for **Today**, **Yesterday**, **Last 7 days**, **Last 14 days**, **Last 30 days**, **This month**, and **Last month** |

Each filter you apply appears as a removable tag beneath the filter row — for example **Service Provider: 5 selected** — so you can see your full filter combination at a glance before running the report. Select **Search** to generate the report once your filters are set.

### Reading the SMS Report

The resulting **SMS Report** table summarizes traffic by provider and date:

| Column | Description |
|---|---|
| **Service Provider** | The provider this row's figures relate to |
| **Date** | The date this row's figures relate to |
| **Total Submitted** | The number of messages submitted to this provider on this date |
| **Delivered** | The number confirmed as delivered |
| **Delivery Failed** | The number that failed to deliver |
| **Pending** | The number still awaiting a final outcome |
| **% Delivery** | The delivery rate for this row, calculated from the figures above |

Select **Download** in the top-right corner of the report to export it for use outside Equify — for example, in a board report or a vendor performance review.

## The Logs tab

The **Logs** tab answers a much more specific question than the Reports tab: *what exactly happened to this one message, or to every message sent to this one number?* Its subtitle reads *"View logs across mobile numbers, messages."*

### Filtering a log search

The **Logs Filter** panel requires more specific input than the Reports filter, and explicitly warns that it **"retrieves logs up to 2 months old."**

| Field | Description |
|---|---|
| **Search Type** *(required)* | The basis for the search, for example **Mobile Number** |
| **Mobile Number** *(required)* | The specific recipient number to search for |
| **Message Pattern** *(optional)* | A wildcard pattern to narrow results by message content |
| **Date Range** *(required)* | The period to search within, using the same calendar control described above |

Select **Search** to run the query. If no records match, Equify displays **"No Logs Found."**

### Reading the SMS Log

The **SMS Log** table is the most granular view of message history available anywhere in the SMS module, with one row per individual message attempt:

| Column | Description |
|---|---|
| **ID** | The unique internal identifier for this message attempt |
| **Mobile No** | The recipient number |
| **Message** | The message content that was sent |
| **Template ID** | The [template](../routing-setup/template-routing.md) used, if any |
| **API Submitted** | The date and time the message was submitted to a provider's API |
| **Service Provider** | The provider used, shown as **Current → Retry** where a [retry](../control-centre/error-retry-management.md) occurred, so you can see at a glance whether a message needed a fallback provider to succeed |
| **API Status** | Whether the provider's API accepted the request (**Success** or **Failed**) |
| **Middleware Status** | The outcome at Equify's own validation layer |
| **Delivery Status** | Whether the message was ultimately confirmed delivered (for example **FAILED**) |
| **Delivery Time** | When the delivery outcome was recorded |
| **DLR Reason** | The raw delivery receipt reason returned by the network, for example **SUCCESS** |
| **Msg Parts** | The number of SMS segments the message was split into |
| **Api Error Code** | The specific error code returned by the provider's API, if any |
| **Middleware Error Code** | The specific error code raised by Equify's own validation layer, if any |

Select **Download** to export the current search results as a CSV file (for example, `Equify_SMS_Logs_2026-06-17_05-33-52_PM.csv`) for offline analysis or for attaching to a support ticket.

## A practical example

A customer support agent receives a complaint that a particular customer never received their OTP. Rather than escalating to engineering, the agent opens **Report & Log**, switches to the **Logs** tab, enters the customer's mobile number and the approximate date, and immediately sees the exact message: which provider it was sent through, whether that provider's API accepted it, what the delivery status was, and — critically — the **DLR Reason** or **Api Error Code** that explains exactly why it failed. What would otherwise be an engineering investigation becomes a two-minute, self-service lookup.

Continue to [Administration](../administration/index.md) to see how Equify tracks changes made to the platform's own configuration, as opposed to changes happening to message traffic.
