# Routing Combinations

Every strategy described so far in this chapter works perfectly well on its own. But real organizations rarely make routing decisions based on just one factor. A bank, for example, might want to check the **department** first, then the **template**, then the **header**, and only fall back to a simple **percentage split** if none of those more specific rules apply. **Routing Combinations** is where you build exactly that kind of layered decision logic — and it is, arguably, the single most powerful screen in the SMS module.

## Opening Routing Combinations

1. In the left-hand navigation menu, select **Routing Setup › Traffic Management**.
2. Select the **Routing Combinations** tab, next to **Strategy Catalog**.

## Understanding the system fallback

Before creating your first combination, Equify displays a permanent reminder at the top of this screen:

> **System Fallback** — *"Round Robin routing automatically serves as the final fallback mechanism for any traffic that does not match specific routing rules."*

This is the same guarantee described in [Round Robin Routing](round-robin.md). No matter how many combinations you build, you can never accidentally create a message that has nowhere to go — Round Robin always catches it.

## Reviewing existing combinations

Below the fallback notice, a table lists every combination strategy that has already been created:

| Column | Description |
|---|---|
| **Strategy Name** | The combination's name, together with a short description of the strategies it chains together — for example, *"RoutingCombination-2"* described as `Template->header->dept->circle->serviceType` |
| **Modified At / Modified By** | When the combination was last changed, and by whom |
| **Status** | A toggle that activates or deactivates the entire combination |
| **Actions** | Reorder or edit the combination |

Use **Search by name or ID…** to find a specific combination once your list grows.

## Building a new combination

1. Select **New Combination** in the top-right corner.
2. In the **Create Combination Routing** panel, complete:

    | Field | Description |
    |---|---|
    | **Combination Name** | A unique name for this combination, for example `RoutingCombination-4`. Names may only contain letters, numbers, hyphens, and underscores |
    | **Description** | A free-text description of what this combination does or is for |

3. Under **Available Routing Strategies**, you will see every strategy covered in this chapter — **Circle Based**, **Department Based**, **Header Based**, **Percentage Based**, **Service Type Based**, and **Template Based** — each with a **+** button. Selecting **+** moves that strategy into the **Execution Sequence** panel on the right, and the counter above the list (for example, *"4 active"*) tracks how many strategies are currently included.
4. In the **Execution Sequence** panel, reorder the selected strategies by dragging the handle (the grid of dots) on the left of each entry. The panel is explicitly labelled **"Top = Top Priority"** — the strategy at the top of the list is evaluated first, and Equify only moves on to the next strategy in the sequence if the one above it does not produce a routing decision for a given message.
5. Remove a strategy from the sequence at any time using the trash-can icon on its row, without losing your other selections.
6. Select **Create Combination** to save.

!!! example "A real four-layer combination"
    A combination built from **Header Based**, **Template Based**, **Department Based**, and **Percentage Based**, in that priority order, behaves as follows for every incoming message: Equify first checks whether the request's header matches a configured rule; if not, it checks whether the message's template matches a rule; if not, it checks the sending department; and if none of those three more specific strategies apply, it finally falls back to the configured percentage split across providers. Only if even that percentage configuration is incomplete does the message fall through to platform-wide Round Robin.

## Why this is the platform's most strategically important screen

Individually, each routing strategy answers one business question. Routing Combinations is what lets your organization encode its *entire* routing policy — every department's preference, every premium template's dedicated route, every regional nuance — into a single, ordered, auditable decision chain that a non-technical administrator can review and adjust in minutes, with Round Robin standing permanently behind all of it as an unconditional safety net. This is the feature that turns Equify from a simple SMS gateway into a genuine enterprise routing engine.

## What's next

This concludes the seven routing strategies documented in this edition of the guide. The **Intelligent Routing** screen, listed alongside Traffic Management in the navigation menu, is a distinct, not-yet-released capability — see [Intelligent Routing](intelligent-routing.md) for what the application currently shows.
