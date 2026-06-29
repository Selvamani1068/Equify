# Introduction to SMS Messaging

This chapter introduces the core ideas you need before you open the application for the first time. If you are already comfortable with how Equify SMS works conceptually, continue to [Signing In and Navigation](navigation.md).

## The journey of a single message

Every SMS that Equify sends follows the same path, regardless of which department triggered it or which provider eventually delivers it:

1. **Origination.** A message is created either by a backend application calling the Equify Message API directly over HTTPS, or by a row being written to a client database table that Equify is configured to watch.
2. **Validation.** Equify's Middleware Service checks that the message has everything it needs — a valid recipient, message body, and any required template or routing information — before it is allowed any further.
3. **Routing decision.** Equify decides which service provider should carry this specific message. This decision can depend on the sending department, the type of service (for example, a one-time password versus a promotional offer), the recipient's region, or a fixed percentage split, depending on how your routing rules are configured. See [Routing Setup](../routing-setup/index.md) for the full set of strategies.
4. **Dispatch.** The Dispatcher Service rewrites the message into the exact request format the chosen provider expects and sends it over HTTPS.
5. **Outcome handling.** If the provider accepts the message, Equify records the response and waits for a delivery receipt. If the provider rejects it or fails to respond, the Retry Service checks your configured retry policy and, where appropriate, automatically tries the next provider in the priority list.
6. **Delivery confirmation.** When the telecom network confirms that the handset received the message, the provider sends a delivery receipt back to Equify, which is matched to the original message and written to your output database.
7. **Reporting.** Every step above leaves a trace that feeds the [Dashboard](../dashboard/index.md), so your team can see exactly how many messages were sent, how many were delivered, and where any failures occurred — often within seconds of it happening.

## Key concepts used throughout this guide

**Service Provider.** A telecom operator or SMS aggregator that Equify has been configured to send messages through — for example, a mobile network operator or a third-party SMS gateway. Each service provider is registered once and can then be referenced anywhere in your routing rules.

**Channel.** The communication medium a service provider is registered for. This guide focuses on the **SMS** channel; Equify also supports a separate **WhatsApp** channel, which is documented elsewhere.

**Service Type.** A classification of the *purpose* of a message — typically **OTP** (one-time passwords for authentication), **Transactional** (account alerts, confirmations, and other non-marketing messages a customer expects), or **Promotional** (marketing and offers). Service type matters because regulators and telecom operators often treat these categories differently, and because OTP messages typically demand much lower latency than promotional traffic.

**Department.** A business unit inside your organization — such as Credit, Loans, Insurance, HR, Sales, Finance, Admin, Operations, or Engineering — that can be assigned its own dedicated routing behavior, so that, for example, the Credit department's OTP traffic can be isolated from the Sales department's promotional traffic.

**Routing Strategy.** A rule that decides which service provider handles a given message. Equify ships with seven distinct strategies, described in full in [Routing Setup](../routing-setup/index.md), and lets you combine several of them into a single prioritized decision chain.

**Delivery Receipt (DLR).** The confirmation message a telecom network sends back after a handset receives an SMS. Equify processes these automatically and uses them to calculate the delivery rate shown on the dashboard.

**Retry Policy.** The set of rules that determines what Equify does when a service provider's API returns an error — whether to retry, and if so, through which alternate provider.

## What you need before you start

Before configuring the SMS module for the first time, your administrator should have:

- At least one **service provider account** with API credentials (a base URL, and either a username and password or a bearer token) supplied by your telecom partner or aggregator.
- Access to the **input database** or backend application that will originate messages, if you intend to send messages by database polling rather than by direct API call.
- A list of the **departments** or business units that should have distinct routing behavior, if your organization needs department-level control.
- Single sign-on access provisioned through your organization's identity provider, since Equify authenticates users through OIDC-based SSO rather than a separate local login.

With these concepts in hand, continue to [Signing In and Navigation](navigation.md) to see how this maps onto the actual screens inside Equify.
