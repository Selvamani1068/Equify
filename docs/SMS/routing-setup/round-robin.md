# Round Robin Routing

Round Robin is the simplest of Equify's seven routing strategies, and the most important one to understand first, because it plays a special role: it is the platform's **automatic, system-wide fallback**.

## What Round Robin does

Round Robin distributes traffic equally across every available service provider, in a continuous circular order — the first message goes to provider A, the second to provider B, the third to provider C, and the cycle repeats — to ensure load balancing across your providers. No single provider is favored over another, and no business context (department, region, or service type) is taken into account.

## Opening Round Robin configuration

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. On the **Strategy Catalog** tab, select **Configure** on the **Round Robin** card.

## Why Round Robin is also the system fallback

Round Robin has a second, equally important job. On the **Routing Combinations** tab of Traffic Management, Equify displays a permanent **System Fallback** notice:

> *"Round Robin routing automatically serves as the final fallback mechanism for any traffic that does not match specific routing rules."*

In practice, this means you do not need to define a catch-all rule yourself. If a message does not match any [Functional Routing](functional-routing.md), [Header Routing](header-routing.md), [Geographic Routing](geographic-routing.md), or other specific rule you have configured, Equify does not reject it or leave it stuck — it automatically distributes it evenly across your active providers using Round Robin. This guarantee is what allows administrators to configure routing incrementally, adding more specific rules over time, without ever risking a message having nowhere to go.

## When to rely on Round Robin alone

Round Robin by itself is a reasonable starting point for an organization that:

- Has only just onboarded its first two or three service providers and has not yet defined department-, region-, or service-type-specific rules.
- Wants simple, even load distribution across providers of genuinely similar cost, quality, and latency.
- Wants a safety net in place before layering more targeted strategies on top, as described in [Routing Combinations](routing-combinations.md).

For most enterprise deployments, Round Robin is used less as the primary strategy and more as the dependable floor beneath a stack of more specific rules — which is exactly the pattern shown in [Routing Combinations](routing-combinations.md).

Continue to [Percentage Allocation](percentage-allocation.md) for a routing strategy that gives you precise, deliberate control over the split, rather than an even one.

---

## What to do next

- Explore other routing strategies in [Routing Overview](index.md)
- Combine strategies in [Create Routing Combinations](routing-combinations.md)