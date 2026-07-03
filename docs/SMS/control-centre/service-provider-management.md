# Service Provider Management

Once one or more service providers have been registered, **SP Management** becomes the screen you return to whenever you need to check a provider's configuration, make it the platform default, temporarily disable it, or review exactly what was set up during registration.

## Opening the list

In the left navigation menu, select **Control Centre › Service Provider (SP) › SP Management**. The **Service Provider Management** screen lists every registered provider.

| Column | Description |
|---|---|
| **SP Name** | The provider's registered name, for example `Equence`, `Airtel`, `Jio`, or `Videocon` |
| **Modified By** | The user who last changed this provider's configuration |
| **Modified At** | When that change was made |
| **Deactivation Reason** | A free-text note explaining why a provider was disabled, if applicable, or `N/A` if the provider has never been deactivated |
| **Status** | A toggle switch that activates or deactivates the provider |
| **Default** | Shows **Yes** for the single provider Equify will use when no other routing rule applies, and **No** for all others |
| **Actions** | View (eye icon) or open routing/configuration settings (gear icon) for that provider |

Use **Search Service Providers Name…** in the top-right corner to find a specific provider once your list grows. Select **Register SP** in the top-right corner at any time to begin the [registration wizard](service-provider-registration.md) for a new provider.

## Reviewing a provider's full configuration

Selecting a provider's name from the list opens its **Service Provider Details** page, a read-only summary of everything configured for that provider during registration:

- **Basic Information** — the provider's name, internal **Service Provider Code**, and **Channel**.
- **API Configurations** — every API configuration registered for this provider, shown as an expandable card per configuration. Each card's header summarizes its HTTP method, service type, and authentication username at a glance (for example `POST` · `Any` · `equify`), and can be expanded with **View configuration details** to see the full **API Details**, **Authentication** fields, a **Sample Request Body**, and the **Mapping Parameters** — split into **Header Parameters** and **API Parameters** — that translate Equify's internal field names into the names this specific provider expects.
- **Response Mappings** — directly beneath the API Configurations, a dedicated panel shows how this provider's responses are interpreted, split into the same three tabs configured during [registration](service-provider-registration.md#step-3-response-mapping): **Success Response**, **Error Response**, and **DLR Response**, each with its own sample JSON for quick reference.
- A provider can carry several API configurations side by side — for example, a primary `POST` / `Any` configuration alongside a second `GET` / `OTP` configuration — and each one carries its own independent **Active** or **Inactive** toggle, so a specific configuration can be turned off without affecting the others.

## Editing a provider

Selecting the edit (pencil) action reopens the same four-step wizard used during [registration](service-provider-registration.md), pre-filled with the provider's current details, so that any field — from the basic service provider details through to individual API request mappings — can be revisited and updated without starting over.

## Activating, deactivating, and setting the default provider

- Toggle a provider's **Status** off to stop Equify from routing any traffic to it, without deleting its configuration. This is the recommended way to temporarily take a provider out of service — for example, during a planned maintenance window communicated by that telecom partner.
- Exactly one provider at a time can be marked **Default**. The default provider is the one Equify falls back to under [Round Robin Routing](../routing-setup/round-robin.md) when no more specific rule applies to a message, so this setting should be reviewed carefully before being changed in a live environment.

Continue to [Error and Retry Management](error-retry-management.md) to define what Equify should do automatically when a provider's API returns an error.

---

## Related articles

- [View Service Provider Details](view-sp-details.md)
- [Service Provider Registration](service-provider-registration.md)