---
layout: decision-record
title: "Choosing a Table-Based Inventory Interface"
subtitle: "Golden Bike Shop System"
record_id: "MSSE601-ADR-table-based-inventory-interface"
course_short: "MSSE-601 · Software Engineering Foundations"
author: "Minnette Johnson"
course_term: "MSSE 601 – Software Engineering Fundamentals | Fall 2026"
week_owned: "Week 4 – Project Component and UI Design"
team: "SEF 1 – NCM Innovators"
decision_status: "Selected"
decision_summary: "Use a table-based inventory interface to help staff find, compare, and manage bike inventory efficiently."
permalink: /msse601/choosing-a-table-based-inventory-interface/
---

# Portfolio Decision Record: Choosing a Table-Based Inventory Interface

**Name:** Minnette Johnson  
**Course:** MSSE 601 – Software Engineering Fundamentals  
**Term:** Fall 2026  
**Week:** Week 4 – Project Component and UI Design  
**Area Owned:** Interface Design and Design Reasoning  
**Project:** Golden Bike Shop System  
**Team:** SEF 1 – NCM Innovators

## Context

The Golden Bike Shop System needs an inventory interface that allows staff to review available bikes, check their status, and access relevant inventory actions. The interface should support everyday work without making staff navigate through unnecessary screens or visual elements.

The interface design decision matters because inventory information needs to be easy to scan and compare. Staff should be able to identify a bike, understand its current status, and locate the appropriate action without unnecessary effort.

The main question was which interface structure would present inventory information clearly while remaining practical to use and maintain.

## Options Considered

### Option 1: Table-Based Inventory Interface

A table presents inventory items in rows, with consistent columns for important information. Potential fields include bike name, bike type, availability, rental status, details, and available actions. Search and filtering can help staff locate specific items.

This approach emphasizes information density, consistency, and direct comparison between inventory items.

### Option 2: Card-Based Inventory Interface

A card-based interface presents each bike as an individual visual item. Cards can emphasize photographs, descriptive details, and prominent actions.

This can be useful when users need to browse visually. However, displaying many cards can require more screen space and make direct comparison between inventory items less efficient.

### Option 3: Hybrid Dashboard and Inventory Interface

A hybrid approach combines summary cards or dashboard elements with a separate inventory list.

This can provide a broad overview and detailed inventory information. However, it introduces additional interface elements and may increase implementation and maintenance complexity without necessarily improving the core inventory workflow.

## Decision

I selected a **table-based inventory interface** for the Golden Bike Shop System.

The interface will organize inventory items into consistent rows and columns, allowing staff to scan records, compare bike information, check availability or rental status, and access relevant actions. Search and filtering should support efficient retrieval as the inventory grows.

The decision prioritizes the practical management of inventory over a presentation focused primarily on visual browsing.

## Reasoning

The table-based approach best fits the primary task: managing and reviewing structured inventory information.

First, a table supports comparison. When key details appear in consistent columns, staff can compare several bikes without opening separate cards or screens.

Second, a table uses screen space efficiently. It can present more inventory records in a single view than a card-based layout, particularly when users are working with a larger collection of bikes.

Third, the structure supports predictable interaction. Staff can learn where information appears and where to find actions because each row follows the same pattern.

Fourth, the approach is appropriate for structured data. Inventory attributes such as bike type, availability, and rental status are easier to scan when presented consistently.

Finally, the table can be extended with search, filtering, clear status indicators, and responsive behavior as the system develops.

A card-based interface remains a reasonable option for a workflow centered on photographs or visual browsing. A hybrid interface could also be justified if dashboard summaries become an important user requirement. For the current inventory-management need, however, the additional visual elements and complexity do not provide enough benefit to outweigh the advantages of a table.

## Consequences and Trade-Offs

### Expected Benefits

- Staff can compare inventory items using consistent columns.
- More records can be visible at once, reducing unnecessary navigation.
- Availability and rental status can be presented in a predictable location.
- Search and filtering can make larger inventories easier to navigate.
- A consistent structure can simplify interface development and maintenance.

### Limitations and Risks

- Tables can become difficult to read on small screens if too many columns are displayed.
- Dense information can overwhelm users if spacing, typography, and status indicators are poorly designed.
- A table may be less engaging than cards when photographs and visual browsing are important.
- Actions must remain clear and accessible without making each row visually cluttered.

### Mitigation

The interface should use readable typography, sufficient spacing, clear column labels, and consistent status indicators. Search and filtering should help users narrow the inventory when needed.

Responsive behavior should also be considered so the interface remains usable on smaller screens. Depending on the final implementation, this may require horizontal scrolling, selective column visibility, or an alternative compact presentation.

These considerations should be addressed through implementation and usability feedback rather than assuming that a table will be effective in every context.

## Review Conditions

The decision should be reviewed if testing or staff feedback shows that users struggle to locate information, understand status indicators, or complete common inventory tasks.

It should also be reconsidered if the system's primary workflow changes toward image-led browsing, mobile-first use, or a dashboard that provides meaningful operational information.

Useful review questions include:

- Can staff find a particular bike quickly?
- Can users compare availability and rental status without confusion?
- Are the available actions easy to identify?
- Does the interface remain usable on smaller screens?
- Do search and filtering support the size and needs of the inventory?

The table-based decision should remain in place while it supports the workflow effectively. It should not be treated as permanent if evidence demonstrates that another approach would better meet user needs.

## Evidence and Authorship

This record documents my contribution to interface design and design reasoning for the Golden Bike Shop System as part of MSSE 601.

The decision was made by comparing the table-based, card-based, and hybrid approaches against the inventory workflow, information density, usability, and implementation complexity. The rationale and trade-offs are recorded so that the decision can be evaluated and revisited as the project evolves.

**AI-use disclosure:** AI assistance may be used to support the organization, editing, or presentation of this record. The project decision, evaluation of alternatives, and responsibility for the submitted work remain with me. Any course-specific disclosure requirements should also be followed.

## Final Reflection

This decision demonstrates that interface design is not only about appearance. It requires understanding what users need to accomplish and selecting a structure that supports those tasks.

For the Golden Bike Shop System, a table-based inventory interface provides a practical starting point for managing structured records. The choice is based on the current requirements, while usability feedback and future changes will determine whether it remains the best fit.
