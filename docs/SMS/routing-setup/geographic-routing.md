# Geographic Routing

In India in particular, but in many other markets too, no single telecom provider has equally strong coverage everywhere. A provider that delivers flawlessly in one state may perform noticeably worse in another. **Geographic Routing** lets Equify account for this directly, by routing messages based on where they are actually going.

## What Geographic Routing does

Geographic Routing optimizes delivery rates by routing traffic based on the source origin, region, or telecom circle. Rather than using the same provider everywhere, you can assign each geographic circle its own dedicated set of providers, chosen for their known strength in that specific area.

## Opening Geographic Routing

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. On the **Strategy Catalog** tab, select **Configure** on the **Geographic Routing** card.

## Reviewing configured circles

The **Geographic Routing Management** screen lists every telecom circle Equify has been configured to route for, with a **Circle Name** and a corresponding mapping action for each row — covering circles such as **Assam** and **AP** (Andhra Pradesh) among others, reflecting the standard telecom circle structure used across the Indian mobile network.

## Mapping a circle to service providers

1. From the circle list, select the mapping action next to the circle you want to configure — for example, **Assam**.
2. The **Configure Geographic Mapping** panel opens, identifying the specific circle in its subtitle (for example, *"Geographic location: Assam"*).
3. Select the checkbox next to every service provider that should handle traffic destined for that circle, using **Search Service Provider's…** to find a specific provider if needed.
4. As with every other mapping panel in this guide, a running confirmation at the bottom of the panel shows exactly how many providers are selected and which circle they will be applied to — for example, *"2 item(s) selected. Will be copied to Assam's Geographic Routing."*
5. Select **Save Mapping** to apply the change to this circle alone, or **Copy to All** to apply the same provider selection across every configured circle.

## A practical example

A national retailer might find that one provider consistently delivers faster in northeastern circles such as Assam, while a competing provider performs better across southern circles such as AP. Geographic Routing lets the retailer encode that real-world knowledge directly into the platform, so that every message benefits from the best available route for its destination, without requiring a manual decision for each campaign.

!!! info "Determining the destination circle"
    Geographic Routing depends on Equify being able to determine which circle a given recipient number belongs to. In most deployments this is derived automatically from the recipient's mobile number, consistent with standard Indian telecom numbering conventions.

Continue to [Routing Combinations](routing-combinations.md) to see how Geographic Routing and the six other strategies in this chapter can be combined into a single, prioritized decision chain.
