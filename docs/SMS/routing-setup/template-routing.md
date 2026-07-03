# Template Routing

Many SMS programs are built around a small number of recurring, pre-approved message templates — a specific OTP format, a specific promotional offer, a specific payment reminder. **Template Routing** lets you attach a routing decision directly to the template itself, so the right provider is used every single time that template is sent, by anyone, from anywhere in the organization.

## What Template Routing does

Template Routing applies pre-configured routing templates to standardize message handling across different campaigns. Once a template is registered with Equify and mapped to a service provider, every message that declares that template ID is routed consistently, without each individual sender needing to know or specify which provider should be used.

## Opening Template Routing

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. On the **Strategy Catalog** tab, select **Configure** on the **Template Routing** card. You can also reach this screen directly through the breadcrumb path **Dashboard › Traffic Management › Template Based**.

## Reviewing configured templates

The **Template Management** screen lists every template registered for routing purposes:

| Column | Description |
|---|---|
| **Template Name** | A short, human-readable name for the template |
| **ID** | The exact template identifier used by the calling application or service provider |
| **Description** | A free-text note describing the template's purpose, such as *"50% discount"* |
| **Modified At / Modified By** | When the template was last changed, and by whom |
| **Status** | A toggle that enables or disables routing for this template |
| **Actions** | Edit the template's details (pencil icon), or open its provider mapping (sliders icon) |

Use **Search templates…** to find a specific entry once your list grows, or select **Add Template** in the top-right corner to register a new one.

## Registering a new template

1. Select **Add Template** in the top-right corner.
2. In the **Add New Template** panel, complete the following fields:

    | Field | Description |
    |---|---|
    | **Template ID** | A unique identifier for this template. Equify suggests a generated value, which can be overridden |
    | **Template Name** | A short, recognizable name, for example *"XYZ-200"* or *"ABC-100"* |
    | **Template Description** | A description of what the template is used for |

3. Select **Add Template** to save. A confirmation banner reading **"Successfully saved template details"** confirms the template has been created, and it immediately appears in the template list.

!!! warning "Template IDs must be unique"
    Equify requires every Template ID to be unique across the platform, and changes to template configuration may take up to one minute to fully propagate. Plan template naming conventions with this uniqueness requirement in mind, particularly in organizations where multiple teams may register templates independently.

## Mapping a template to service providers

Once a template has been created, use its mapping action (sliders icon) to open the **Configure Template Mapping** panel and select which service providers should handle traffic for that specific template, following the same pattern used in [Functional Routing](functional-routing.md) and [Header Routing](header-routing.md): select the desired providers by checkbox, then **Save Mapping** for this template alone, or **Copy to All** to apply the same providers to every other configured template.

## A practical example

A retail bank running a fixed, pre-approved "50% discount" promotional template can register that template once, map it permanently to a cost-efficient promotional provider, and rely on Equify to route every future send of that exact template correctly — regardless of which marketing team member or which scheduling tool ultimately triggers the campaign.

Continue to [Service Type Routing](service-type-routing.md) to route based on the broader purpose of a message — OTP, transactional, or promotional — rather than a specific template.

---

## What to do next

- Explore other routing strategies in [Routing Overview](index.md)
- Combine strategies in [Create Routing Combinations](routing-combinations.md)