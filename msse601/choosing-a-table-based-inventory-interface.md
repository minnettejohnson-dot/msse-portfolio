
---
layout: decision-record
title: "Choosing a Table-Based Inventory Interface"
subtitle: "Golden Bike Shop System"
record_id: "MSSE601-ADR-table-based-inventory-interface"
course_short: "MSSE-601 · Software Engineering Fundamentals"
author: "Minnette Johnson"
course_term: "MSSE 601 – Software Engineering Fundamentals | Fall 2026"
week_owned: "Week 4 – Project Component and UI Design"
team: "SEF 1 – NCM Innovators"
decision_status: "Selected"
decision_summary: "A table-based inventory interface with search and filters to help staff compare e-bikes across four store locations."
permalink: /msse601/choosing-a-table-based-inventory-interface/
---

## 1. Context {#context}

The Golden Bike Shop system requires staff to manage e-bike inventory across four store locations. Store clerks need to locate available bikes, compare their status and location, review bike details, and initiate rentals without navigating unnecessarily between screens.

As the Interface Design and Design Reasoning Lead, I evaluated how the inventory information should be presented to support these tasks. The central design question was whether staff should view bikes individually through a card-based interface or compare multiple bikes in a table.

This decision mattered because inventory management is a frequent operational task. The interface needed to make relevant information easy to find while reducing unnecessary navigation and the risk of selecting a bike with the wrong status or location.

## 2. Options {#options}

### Option 1: Card-Based Inventory Interface

Each bike would appear in its own card, allowing its information to be presented individually with greater visual emphasis. However, comparing several bikes could require staff to scan multiple cards and potentially scroll through the inventory.

### Option 2: Table-Based Inventory Interface

Multiple bikes would appear in rows, with consistent columns for bike, type, status, rental status, location, and available actions. Search and filter controls would help staff narrow the inventory to relevant bikes.

The main disadvantage would be greater information density, which could make the screen feel crowded.

## 3. Decision {#decision}

I selected the table-based inventory layout for the Golden Bike Shop inventory screen, supported by search and filter controls.

The table presents key bike information together so staff can compare multiple bikes without opening each one individually. The design also provides a consistent place to identify a bike's status and location and access its available actions.

This choice was based on the primary staff workflow rather than visual preference alone. The inventory screen needed to support quick comparison and selection, so I prioritized information visibility and efficient navigation over the more individualized presentation offered by cards.

## 4. Reasoning {#reasoning}

I evaluated the alternatives against the system's inventory requirements and the way staff would use the interface during daily operations.

The table-based design supports recognition rather than recall because staff can see several bikes and their relevant attributes together. This reduces the need to remember information from one screen while inspecting another. It also supports faster comparison of status and location, helping staff identify suitable bikes before initiating a rental.

The card-based alternative offered a legitimate benefit: each bike could receive more visual space, making individual details easier to emphasize. However, the principal inventory task involved comparing multiple bikes, not simply inspecting one bike at a time. I therefore judged the table to be the better fit for the primary workflow.

I also recognized that a table could become visually dense. I addressed this trade-off by incorporating search and filtering controls, allowing staff to narrow the displayed results rather than relying entirely on scanning every row.

The decision was therefore a balance between comparison efficiency and information density. I accepted the denser presentation because it better supported the inventory task, while using search and filters to make the information easier to navigate.

## 5. Consequences {#consequences}

The decision provides staff with a consolidated inventory view that supports searching, filtering, comparing bike information, and accessing relevant actions. It also establishes a consistent starting point for the related Bike Details/Edit and New Rental workflows.

The main cost is that a table presents more information simultaneously than an individual card. If the inventory grows substantially or staff begin using smaller screens, readability and navigation may become more challenging.

The design should therefore be revisited if usability testing shows that staff struggle to locate information, compare bikes, or use the interface on different screen sizes.

Possible improvements could include responsive table behavior, adjustable columns, or a card-based alternative for narrow displays without abandoning the table's advantages for desktop inventory management.

## Evidence and Traceability {#evidence}

- **Week:** Week 4 – Project Component and UI Design.
- **Individual Ownership:** Interface Design and Design Reasoning Lead, as identified in the Week 4 AI Use Record, Entry 4.
- **Deliverable:** Golden Bike Shop Project – Week 4 Project Component and UI Design, submitted September 20, 2026.
- **Decision Location:** Section 5, Team Decision Record, Decision 1: Inventory Layout.
- **Supporting Evidence:** Section 2, Screen 1 – Inventory Management; Section 3, Design Reasoning; and the AI Use Record, Entry 4.
- **AI-Use Disclosure:** ChatGPT was used to compare table-based and card-based inventory designs against the project requirements and identify their respective strengths, weaknesses, and trade-offs. I used that analysis to evaluate the alternatives and strengthen the written rationale. The selected table-based design was retained because it best supported the staff workflow of comparing multiple bikes. The AI assisted with analysis; it did not replace my responsibility for evaluating the alternatives and documenting the design decision.
