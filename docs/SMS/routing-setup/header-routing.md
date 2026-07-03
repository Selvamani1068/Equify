# Header Routing

Functional Routing decides a provider based on which department sent a message. **Header Routing** takes a more technical approach: it inspects the HTTP request itself, at the moment a message is submitted, and lets the calling application signal which route it wants.

## What Header Routing does

Header Routing inspects HTTP headers dynamically to determine the optimal downstream provider for each request. Each configured header is associated with one or more service providers, so that any application calling the Equify Message API can request a specific routing behavior simply by including the correct header in its request, without needing any separate configuration on the application side.

## Opening Header Routing

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. On the **Strategy Catalog** tab, select **Configure** on the **Header Routing** card. You can also reach this screen directly through the breadcrumb path **Dashboard › Traffic Management › Header Based**.

## Reviewing configured headers

The **Header Management** screen lists every header Equify has been configured to recognize:

| Column | Description |
|---|---|
| **Header Name** | A short, code-like identifier such as `EQUENC`, `AIRTEL`, `FINBKK`, `Videocon`, `ICICIB`, or `AXISBK` |
| **Description** | A plain-language label, such as *"Equence Header"* or *"ICICI Bank Header"* |
| **Code** | The exact header value calling applications must send |
| **Modified At / Modified By** | When the header was last changed, and by whom |
| **Status** | A toggle that enables or disables routing for this header |
| **Actions** | Edit the header's details (pencil icon), or open its provider mapping (sliders icon) |

Use **Search headers…** to find a specific entry, or select **Add Header** in the top-right corner to define a new one.

!!! example "A header for a specific business relationship"
    The list of headers configured in a live environment often reflects specific partner or client relationships rather than generic categories — for example, separate headers for `FINKBK` (a banking partner), `ICICIB` and `AXISBK` (named banks), and `123456` mapped to the description *"promo"* for promotional traffic. This makes Header Routing especially well suited to organizations that operate as a platform on behalf of several distinct end clients, each of whom should be routed differently.

## Mapping a header to service providers

1. From the header list, select the mapping action (the sliders icon) next to the header you want to configure.
2. The **Configure Header Mapping** panel opens, identifying the specific header being configured.
3. Select the checkbox next to every service provider that should handle requests carrying this header, using **Search Service Provider's…** to find a specific entry if needed.
4. Select **Save Mapping** to apply your change to this header only, or **Copy to All** to apply the same provider selection to every other configured header.

A confirmation banner reading **"Header Routing Strategy Updated Successfully"** confirms the change has been applied.

## When to use Header Routing instead of Functional Routing

Functional Routing and Header Routing solve a similar problem from two different directions. Functional Routing is the right choice when your *department* is the deciding factor and that department always uses the same backend application. Header Routing is the better choice when a single shared application serves many different purposes, and the application itself — rather than the department that happens to be using it — needs to specify the route on a per-request basis.

Continue to [Template Routing](template-routing.md) to route based on the specific message template being sent, rather than the request that carries it.

---

## What to do next

- Explore other routing strategies in [Routing Overview](index.md)
- Combine strategies in [Create Routing Combinations](routing-combinations.md)