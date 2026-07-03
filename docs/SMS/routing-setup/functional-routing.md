# Functional Routing

Most enterprises do not think of SMS traffic as one undifferentiated stream — they think of it as the Credit team's OTPs, the Sales team's promotions, and the HR team's notifications, each with potentially different requirements. **Functional Routing** lets Equify reflect that reality directly in its routing rules.

## What Functional Routing does

Functional Routing routes specific traffic based on business functions, internal departments, or operational units. Once a department is defined and mapped to one or more service providers, every message tagged with that department is routed accordingly — independently of whatever rules apply to every other department.

## Opening Functional Routing

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. On the **Strategy Catalog** tab, select **Configure** on the **Functional Routing** card. You can also reach this screen directly through the breadcrumb path **Dashboard › Traffic Management › Functional Based**.

## Reviewing configured departments

The **Functional Routing** screen lists every department Equify has been configured to recognize:

| Column | Description |
|---|---|
| **Department Name** | A short, code-like name such as `CREDIT`, `LOAN`, `INSURANCE`, `HR`, `SALES`, `FINANCE`, `ADMIN`, `OPERATIONS`, or `ENGINEERING` |
| **Description** | A plain-language description, such as *"Credit Department"* |
| **Code** | A numeric identifier assigned to the department |
| **Modified At / Modified By** | When the department was last changed, and by whom |
| **Status** | A toggle that enables or disables routing for this department |
| **Actions** | Edit the department's details (pencil icon), or open its provider mapping (the icon resembling a set of sliders) |

Use **Search departments…** to find a specific entry, or select **Add Department** in the top-right corner to define a new one.

## Mapping a department to service providers

1. From the department list, select the mapping action (the sliders icon) next to the department you want to configure — for example, **CREDIT**.
2. The **Configure Functional Mapping** panel opens, showing the department name in its subtitle (for example, *"Department: CREDIT"*).
3. Use **Search Service Provider's…** to find a specific provider, or scroll the list of every registered provider, each shown with its **Name** and **Code**.
4. Select the checkbox next to every provider that should handle this department's traffic. The panel keeps a running count at the bottom — for example, *"1 item(s) selected. Will be copied to CREDIT's functional Routing"* — confirming exactly what is about to be saved.
5. Select **Save Mapping** to apply your changes to this department only, or **Copy to All** to apply the same provider selection to every other configured department in one action — a useful shortcut when most departments should share the same default provider, with only a few exceptions configured individually afterward.

## A practical example

A bank might map its **CREDIT** and **LOAN** departments — both of which send time-sensitive OTPs and account alerts — to its most reliable, lowest-latency provider, while mapping **SALES** and **HR**, which send a higher volume of less time-sensitive notifications, to a lower-cost provider. Functional Routing makes this distinction enforceable at the platform level, rather than relying on each department's own application to make the right choice every time.

Continue to [Header Routing](header-routing.md) to see how routing decisions can instead be driven by the calling application itself, at the moment a message is submitted.

---

## What to do next

- Explore other routing strategies in [Routing Overview](index.md)
- Combine strategies in [Create Routing Combinations](routing-combinations.md)