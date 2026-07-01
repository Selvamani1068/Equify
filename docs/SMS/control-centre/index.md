# Control Centre Overview {#control_centre}

The **Control Centre** is where the SMS module is configured rather than monitored. If the Dashboard answers *"is everything working right now?"*, the Control Centre answers *"how is everything set up?"* Almost every administrative task in the SMS module — connecting a database, onboarding a telecom partner, or defining what happens when a message fails — starts here.

## Opening the Control Centre

Select **Control Centre** in the left-hand navigation menu. It expands to reveal two groups of sub-pages.

## What the Control Centre contains

| Section | Sub-pages | What it is for |
|---|---|---|
| **Platform DB Setup** | DB Configuration, DB Management | Connecting Equify to the databases your applications already use, so that messages can be sent and delivery results recorded without writing custom integration code |
| **Service Provider (SP)** | SP Registration, SP Management, Error Control Center | Onboarding telecom partners and aggregators, managing their credentials and API behavior, and defining what Equify should do when a partner's API returns an error |

The remainder of this section walks through each of these in the order a new administrator would typically use them: connecting a database first, then onboarding a service provider, then defining how errors from that provider should be handled.

## Who should have access

Because every setting in the Control Centre affects how live customer messages are sent, access to this section should be limited to a small number of trusted platform administrators — typically the same team responsible for integrating Equify with your core business applications and managing your telecom vendor relationships. Day-to-day operations staff should generally only need the [Dashboard](../dashboard/index.md).

Continue to [Platform Database Setup](database-setup.md) to begin.
