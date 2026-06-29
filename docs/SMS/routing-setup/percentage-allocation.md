# Percentage Allocation

Where [Round Robin](round-robin.md) splits traffic evenly without judgment, **Percentage Allocation** gives you precise, deliberate control over exactly what share of your traffic each service provider receives.

## What Percentage Allocation does

Percentage Allocation routes traffic based on specific probability percentages assigned to each service provider, for precise volume control. Rather than every provider receiving an equal share, you decide the exact split — for example, sending half of all traffic to one provider and half to another, or gradually increasing a new provider's share from a small starting percentage while you build confidence in its reliability.

## Opening Percentage Allocation

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. On the **Strategy Catalog** tab, select **Configure** on the **Percentage Allocation** card. You can also reach this screen directly through the breadcrumb path **Dashboard › Traffic Management › Percentage Based**.

## Setting a percentage split

The **Percentage Allocation** screen lists every registered service provider in a table:

| Column | Description |
|---|---|
| **Service Provider ID** | The provider's internal identifier |
| **Service Provider Name** | The provider's registered name |
| **Service Provider Code** | The short code generated for the provider, for example `equi101` or `jio103` |
| **Current Percentage** | The percentage of traffic currently assigned to this provider |
| **Set Percentage** | An editable field where you enter the new percentage you want this provider to receive |

To change the split, enter a new value into the **Set Percentage** field for each provider you want to adjust, then select **Save Distribution** in the top-right corner of the screen.

## Tracking your progress with the distribution summary

As you adjust percentages, the **Percentage Distribution Summary** bar at the top of the screen updates in real time, showing:

- What percentage of the total 100% has currently been allocated (for example, **100% complete**).
- Which provider currently holds the **Highest** share, and what that share is (for example, **Highest: 50% (Equence)**).
- How many service providers currently have a non-zero allocation (for example, **2 service providers configured**).

!!! tip "The split must add up to 100%"
    Equify expects your percentages across all providers to total 100%. A common, safe pattern is to split traffic between exactly two providers — for example 50% and 50%, as shown in a typical configuration — while leaving every other registered provider at 0%, rather than spreading a small percentage across many providers at once.

## A practical example

Imagine your organization currently sends all OTP traffic through a single long-standing provider, and you want to test a second provider without risking a sudden, full cutover. You could configure Percentage Allocation to send 90% of traffic to the existing provider and 10% to the new one, monitor the new provider's [delivery rate and latency](../dashboard/service-providers.md) for a few days, and then gradually increase its share as confidence grows — all without writing a single line of code or involving your development team.

Continue to [Functional Routing](functional-routing.md) to route traffic based on which part of the business it comes from, rather than by a fixed split.
