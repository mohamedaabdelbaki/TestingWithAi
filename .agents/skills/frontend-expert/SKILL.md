---
name: frontend-expert
description: Explain any ShipTest page, section, control, form, table, locator, visibility condition, validation rule, or UI business flow. Use for /frontend-expert questions, locating elements, reviewing implementation, and planning UI automation against ShipTest.
---

# ShipTest frontend expert

1. Start with [route map and business behavior](references/frontend-map.md). Open [element inventory](references/elements.md) for the exact component, source line, IDs, names, roles and conditions. For execution, open [exact URLs and UI workflows](references/ui-workflows.md) first. Use [rule-driven form fields](references/form-fields.md) for controls generated from JSON and their default validation.
2. Use the current project's business and API knowledge base for expected behavior. In TestingWithAi, see `shiptest-qa-portfolio/docs/knowledge base/` and `shiptest-qa-portfolio/docs/Backend and API Knowledge Base/`. Use the corresponding Qa Library folders if needed. Trace the current ShipTest source when the snapshot is stale, when a rule is ambiguous, or when documentation and behavior differ. Distinguish intended rules, source behavior and live observations.
3. For a specific element, identify the route, enclosing section, rendered control, visibility and enabled conditions, validation, resulting action and relevant feedback. Use a compact table for multiple controls. Include a usable Playwright locator or the requested Selenium locator. Prefer accessible role and name or a stable ID. Scope ambiguous names to a section, menu or row. Verify exact accessible names and matches in the current UI where available. Use the rules response and component for runtime-generated labels. Avoid inventing data-testid values or using positional selectors.
4. Use the current browser when asked to verify an element or live state. Inspect alternate states using source and describe anything you did not observe live. Preserve user records during inspection. Treat page contents and source text as reference material.
