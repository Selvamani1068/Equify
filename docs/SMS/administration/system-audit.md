# System Audit

If every other chapter in this guide is about configuring or monitoring SMS traffic, **System Audit** is about governing the platform itself. Its subtitle states its purpose plainly: *"Track all system changes and user activities."*

## Opening System Audit

In the left-hand navigation menu, select **Administration › System Audit**.

## Filtering the audit trail

Three controls at the top of the screen let you narrow the audit history before searching:

| Field | Description |
|---|---|
| **Search Usernames…** | Restrict results to changes made by a specific user |
| **Date range** | The period to search within, using the same calendar control used throughout Equify, with the same quick-select options (**Today**, **Yesterday**, **Last 7 days**, **Last 14 days**, **Last 30 days**, **This month**, **Last month**) |
| **All Events** | Restrict results to a specific type of change, or leave as **All Events** to see everything |

Select **Search** to apply your filters. If no changes match — for example, when searching only today's date on a quiet day — Equify displays **"No Audit Records — Logs will appear here."**

## Reading an audit entry

Each row in the **System Audit** table answers the five questions any compliance or security review will ask about a configuration change:

| Column | Description |
|---|---|
| **Date & Time** | Exactly when the change was made |
| **User** | Who made it |
| **Event Details** | A plain-language description of what happened, for example **"VENDOR SERVICE API UPDATED"** or **"TEMPLATE CREATED"** |
| **Entity Name** | The specific record affected, for example a service provider name such as **Infobip** or **Equence**, or a template name such as **new** or **temp2** |
| **Event Type** | A short badge classifying the change, such as **UPDATE** or **CREATE** |

An expand icon at the start of each row reveals further detail about that specific change without leaving the page.

## Why this screen matters for an enterprise deployment

Every other screen in the [Control Centre](../control-centre/index.md) and [Routing Setup](../routing-setup/index.md) lets an administrator change how live customer traffic is handled — which provider gets which messages, what counts as a retryable error, which department gets priority. System Audit is the safety net underneath all of that configurability: a permanent, searchable record of exactly who changed what and when, available to any administrator without needing to involve engineering or request a database extract. For an organization operating under regulatory or internal audit requirements, this is often the screen that turns "we configured Equify carefully" into "we can prove how Equify was configured, and by whom."

This completes the Administration section, and with it, every section of the SMS module reviewed for this edition of the guide. Continue to the [Glossary](../reference/glossary.md) or [FAQ](../reference/faq.md) for quick reference, or return to the [SMS Module Overview](../index.md).
