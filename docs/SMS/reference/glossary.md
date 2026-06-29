# Glossary

| Term | Definition |
|---|---|
| **Channel** | The communication medium a service provider is registered for inside Equify — for example **SMS** or **WhatsApp** |
| **Configuration Summary** | A read-only panel that mirrors a form's currently saved settings, used throughout the Control Centre to confirm what Equify has on record |
| **Delivery Rate** | The percentage of sent messages confirmed as delivered to a recipient's handset |
| **Delivery Receipt (DLR)** | The confirmation message a telecom network sends back after a handset receives an SMS |
| **DLR Reason** | The raw delivery outcome text returned by the telecom network in a delivery receipt, visible per message in the [SMS Log](../analytics/report-and-log.md) |
| **Department** | A business unit, such as Credit, Loans, Sales, or HR, that can be assigned its own dedicated routing behavior through [Functional Routing](../routing-setup/functional-routing.md) |
| **DLR Processing Engine** | The part of the Equify architecture responsible for matching incoming delivery receipts to their original messages and recording the outcome |
| **Dispatcher Service** | The Equify service responsible for translating a message into a specific provider's API format and sending it |
| **Failure Rate** | The percentage of sent messages that did not deliver successfully, broken down on the Dashboard into Middleware, API, and Delivery failure categories |
| **Functional Routing** | A routing strategy that routes traffic based on business department or operational unit |
| **Geographic / Circle Routing** | A routing strategy that routes traffic based on the recipient's region or telecom circle |
| **Header Routing** | A routing strategy that routes traffic based on a custom HTTP header included in the originating request |
| **Identity Provider (IDP)** | Your organization's existing single sign-on system, used to authenticate Equify users via OIDC |
| **Intelligent Routing** | A routing capability listed under Routing Setup that is confirmed, within the application, as not yet released — see [Intelligent Routing](../routing-setup/intelligent-routing.md) |
| **Kafka Cluster** | The message queue at the core of Equify's Message Processing Engine, which guarantees ordered, reliable delivery of messages between internal services |
| **Latency** | The time between a message being dispatched to a service provider and a response being received |
| **Message API** | The HTTPS API that backend applications can call directly to submit a message to Equify, as an alternative to database-based integration |
| **Middleware Service** | The Equify service responsible for validating an incoming message before it is routed to a provider |
| **Msg Parts** | The number of individual SMS segments a single message was split into, shown per message in the [SMS Log](../analytics/report-and-log.md) |
| **Percentage Allocation** | A routing strategy that splits traffic across providers according to administrator-defined percentages |
| **Response Mapping** | The configuration, set during [Service Provider Registration](../control-centre/service-provider-registration.md), that tells Equify how to recognize success, error, and delivery responses from a specific provider's API |
| **Retry Policy** | The configured set of rules determining whether, and through which alternate provider, Equify retries a message after a service provider error |
| **Round Robin** | A routing strategy that distributes traffic evenly across all available providers, and which also serves as Equify's platform-wide fallback for unmatched traffic |
| **Routing Combination** | A saved, prioritized chain of two or more individual routing strategies, configured under [Routing Combinations](../routing-setup/routing-combinations.md) |
| **Service Provider (SP)** | A telecom operator or SMS aggregator registered inside Equify to carry outbound messages |
| **Service Type** | A classification of message purpose — **OTP**, **Transactional**, or **Promotional** — used by [Service Type Routing](../routing-setup/service-type-routing.md) |
| **System Audit** | The Administration screen that records every configuration change made across the SMS module, by every user — see [System Audit](../administration/system-audit.md) |
| **System Fallback** | The guarantee that Round Robin routing automatically handles any message that does not match a more specific configured rule |
| **Template Routing** | A routing strategy that routes traffic based on a pre-registered message template ID |
| **TPS (Transactions Per Second)** | The rate at which Equify is sending messages at a given moment, shown live on the Dashboard |
