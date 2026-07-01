# Routing Setup Overview {#routing}

If the [Control Centre](../control-centre/index.md) is where you tell Equify *who* your service providers are, **Routing Setup** is where you tell Equify *which provider should carry which message*. This is the section that turns a list of telecom partners into an intelligent, business-aware delivery strategy.

## Opening Routing Setup

In the left-hand navigation menu, select **Routing Setup**. It expands to reveal **Traffic Management** and **Intelligent Routing**.

=== "Traffic Management"

    ## Traffic Management

    Selecting **Traffic Management** opens a screen with two tabs: **Strategy Catalog** and **Routing Combinations**.

=== "Routing Combinations"

    ### Routing Combinations

    The **Routing Combinations** tab lets you chain multiple strategies into a single, prioritized decision — for example, checking the department first, then the circle, then the service type, before finally falling back to a percentage split. This is covered in full in [Routing Combinations](routing-combinations.md), the most advanced chapter in this section.

### The Strategy Catalog

The **Strategy Catalog** presents seven distinct routing strategies as a set of cards, each with a short description and a **Configure** link:

| Strategy | What it does | Typical use case |
|---|---|---|
| [**Round Robin**](round-robin.md) | Distributes traffic equally across all available providers in a circular order, to ensure load balancing | The platform-wide default fallback for traffic that matches no other rule |
| [**Percentage Allocation**](percentage-allocation.md) | Routes traffic based on specific probability percentages assigned to each provider, for precise volume control | Gradually shifting volume from an incumbent provider to a new one |
| [**Functional Routing**](functional-routing.md) | Routes specific traffic based on business functions, internal departments, or operational units | Giving the Credit department a different provider than the Sales department |
| [**Header Routing**](header-routing.md) | Inspects HTTP headers dynamically to determine the optimal downstream provider for each request | Letting the calling application specify its preferred route at the point of integration |
| [**Template Routing**](template-routing.md) | Applies pre-configured routing templates to standardize message handling across different campaigns | Standardizing how a specific, recurring message template (such as a promotional campaign) is always routed |
| [**Service Type Routing**](service-type-routing.md) | Segregates and prioritizes traffic based on service types like OTP, Transactional, or Promotional | Ensuring OTP messages always use your fastest, most reliable providers |
| [**Geographic Routing**](geographic-routing.md) | Optimizes delivery rates by routing traffic based on the source origin, region, or telecom circle | Using the provider with the strongest local network in a specific state or circle |

Each strategy can be configured independently, and most organizations end up using several of them together — which is exactly what the second tab is for.

### Routing Combinations

The **Routing Combinations** tab lets you chain multiple strategies into a single, prioritized decision — for example, checking the department first, then the circle, then the service type, before finally falling back to a percentage split. This is covered in full in [Routing Combinations](routing-combinations.md), the most advanced chapter in this section.

## Intelligent Routing

**Intelligent Routing**, listed in the navigation menu alongside Traffic Management, is confirmed as a not-yet-released, in-development feature — the application itself displays a "Coming Soon" screen when this section is opened. See [Intelligent Routing](intelligent-routing.md) for full details of what is currently shown.

## How to think about routing as a whole

A useful mental model is that Equify evaluates routing rules the way a business analyst would read a decision table from top to bottom: the most specific applicable rule wins, and if nothing specific applies, traffic falls through to Round Robin so that no message is ever left without a provider. The [Routing Combinations](routing-combinations.md) chapter shows exactly how that ordering is configured in practice.

Continue to [Round Robin Routing](round-robin.md) to begin with the platform's foundational strategy.
