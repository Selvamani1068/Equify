# Service Type Routing

Not every SMS your organization sends carries the same urgency. A one-time password that arrives thirty seconds late is a failed login; a promotional offer that arrives thirty seconds late makes no difference at all. **Service Type Routing** lets Equify treat these categories of traffic differently, on purpose.

## What Service Type Routing does

Service Type Routing segregates and prioritizes traffic based on service types like OTP, Transactional, or Promotional. Rather than every message competing for the same providers under the same conditions, each service type can be assigned its own dedicated set of providers — typically your fastest and most reliable providers for OTP traffic, and more cost-efficient providers for promotional traffic where a few extra seconds of latency carries no real business cost.

## Opening Service Type Routing

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. On the **Strategy Catalog** tab, select **Configure** on the **Service Type Routing** card. You can also reach this screen directly through the breadcrumb path **Dashboard › Traffic Management › Service Types**.

## The three service types

Unlike departments, headers, or templates, Equify's service types are fixed and built into the platform rather than something you create yourself. The **Service Type Management** screen lists exactly three entries:

| Service Type Name | Description |
|---|---|
| **OTP** | Otp Messages |
| **Promotional** | Promotional Messages |
| **Transactional** | Transactional Messages |

Because these three categories are standard across the platform, this screen has no **Add** button — your work here is limited to mapping each of the three existing service types to the providers you want to handle them, using the mapping action (sliders icon) next to each row.

## Mapping a service type to providers

1. From the service type list, select the mapping action next to the service type you want to configure — for example, **OTP**.
2. The **Configure Service Mapping** panel opens, identifying the service type in its subtitle (for example, *"Service Type: OTP"*).
3. Select the checkbox next to every service provider that should be eligible to carry this type of traffic. As with the other mapping panels in this guide, a running count confirms your selection — for example, *"3 item(s) selected. Will be copied to OTP's Service Type Routing."*
4. Select **Save Mapping** to apply the change to this service type alone, or **Copy to All** to apply the same provider selection across all three service types.

## A practical example

A typical configuration maps **OTP** to a small, carefully chosen set of the most reliable providers available — since every additional provider in an OTP chain is another opportunity for delay — while mapping **Promotional** to a wider pool of providers selected mainly for cost efficiency. **Transactional** messages, which sit between the two in urgency, are often mapped to a similar set of providers as OTP, but with a longer list of acceptable fallbacks.

!!! info "Service type and message classification"
    For Service Type Routing to work correctly, every message Equify processes needs to be correctly tagged with its service type at the point it is created — whether that tag comes from a [Template Routing](template-routing.md) mapping, a database column mapped during [Platform Database Setup](../control-centre/database-setup.md), or a field supplied directly through the Message API.

Continue to [Geographic Routing](geographic-routing.md) to route based on where in the country a message is going, rather than what kind of message it is.
