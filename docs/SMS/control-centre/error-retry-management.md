# Error and Retry Management

No telecom partner has perfect uptime, and every API occasionally returns an error. **Error and Retry Management**, found under the **Error Control Center** in the navigation menu, is where you decide what Equify should do automatically when that happens — without waiting for a human to notice and intervene. This is one of the features most responsible for Equify's reliability at enterprise scale.

## Opening Error and Retry Management

In the left-hand navigation menu, select **Control Centre › Service Provider (SP) › Error Control Center**. The **Error & Retry Management** screen opens.

## Selecting a service provider

At the top of the screen, the **Select Service Provider** control lets you choose which registered provider's error and retry behavior you are configuring — for example, **Equence**. Every setting below this control applies only to the provider currently selected, so each provider can have entirely independent error handling rules.

Beneath the provider selector, two tabs divide the screen: **Retry Management** and **Error Management**.

## Error Management

The **Error Management** tab is where you teach Equify to recognize the specific error codes your selected provider's API can return, and decide whether each one should trigger an automatic retry.

### Reviewing existing error codes

The error table lists every error code configured for the selected provider:

| Column | Description |
|---|---|
| **Retry** | A toggle indicating whether this specific error code should trigger an automatic retry |
| **Error Code** | The exact code or string returned by the provider's API, for example `404`, `407`, or `409` |
| **Message** | A human-readable description of what the error means, for example *"Not Found"* or *"Invalid words used in message"* |
| **Actions** | Edit (pencil) or delete (trash can) this error code |

Use **Search error codes or messages…** to find a specific entry once your list grows.

### Adding a single error code

1. Select **Add Error** in the top-right corner.
2. In the **Configure New Error** panel, complete:

    | Field | Description |
    |---|---|
    | **Error Code** | The exact code your provider returns, for example `ERR500`, `404`, or `TIMEOUT` |
    | **Error Message** | A description of the error condition, used throughout the rest of the application |
    | **Enable Retry** | A toggle that, when on, automatically retries requests when this specific error occurs |

3. Select **Add Error** to save.

!!! warning "Rules for error codes"
    Error codes must be unique per service provider and may only contain letters, numbers, hyphens, and underscores, up to a maximum of 20 characters. Changes to error configuration may take up to one minute to take effect across the platform.

### Adding error codes in bulk

For providers with a large or already-documented list of error codes, Equify supports a bulk upload workflow rather than adding codes one at a time:

1. Select **Download Template** to download a spreadsheet template with three columns: **Error Code**, **Error Description**, and **Retry On**.
2. Complete the template, adding one row per error code, and save the file.
3. Select **Upload Errors** and choose the completed file to import every row in a single action.

This is the recommended approach whenever onboarding a new service provider whose API documentation already lists its full set of error responses.

## Retry Management

Where Error Management defines *which* errors should be retried, **Retry Management** defines *where a retry should go* — the ordered list of alternate service providers Equify should try, in sequence, when the originally selected provider's API fails.

1. Select the **Retry Management** tab.
2. Under **Select Service Providers**, choose every provider that should be eligible to receive a retried message. Each selected provider appears as a removable tag, and the control shows how many providers remain available to add.
3. Each selected provider then appears in the **Priority** table below, in the order Equify will try them:

    | Column | Description |
    |---|---|
    | **Priority** | A numbered position, with 1 being attempted first |
    | **Service Provider** | The provider's name and SP Code |
    | **Actions** | Remove this provider from the retry chain |

4. Reorder providers by dragging the handle (the grid of dots) on the left of each row. For example, a chain might be configured as 1. Jio, 2. Videocon, 3. Airtel — meaning that if a message fails through Jio and the error is configured to retry, Equify automatically attempts Videocon next, and Airtel after that if Videocon also fails.
5. Select **Save** to apply the retry chain.

!!! info "How this fits into the bigger picture"
    Retry Management defines the fallback order for a single provider's failures. The platform-wide safety net beneath all of this is [Round Robin Routing](../routing-setup/round-robin.md), which automatically catches any message that does not match a specific routing rule at all. Together, these two mechanisms are why a single telecom partner having a bad day does not need to mean a single customer misses their OTP.

This completes the Control Centre. Continue to [Routing Setup Overview](../routing-setup/index.md) to learn how traffic is actually distributed across your configured providers.

---

## What to do next

- Review system logs in [Analytics](../analytics/index.md)
- Optimize routing in [Routing Setup](../routing-setup/index.md)