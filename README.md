# TestingWithAi

Practical QA projects using AI for requirements analysis, test design, and incident investigation.

- [ShipTest QA Portfolio](shiptest-qa-portfolio/README.md) — shipping business rules, API and database reference, and a simulated shipment incident.
- [API and database reference](shiptest-qa-portfolio/docs/knowledge%20base/api-and-backend/README.md) — endpoint contracts and database behavior.
- [Frontend reference](shiptest-qa-portfolio/docs/knowledge%20base/frontend/README.md) — ShipTest URLs, locators, form rules, and UI workflows.
- [Sample test reports](sample%20ai%20projects/reports/) — test cases and a dashboard.
- [Sample incident logs](sample%20ai%20projects/logs/) — service logs and incident evidence.

## ShipTest skills

- [Business Expert](.agents/skills/business-expert/SKILL.md) — answers questions about the app's business rules and implementation.
- [Update the ShipTest knowledge base](.agents/skills/upadated-knowledge-base/SKILL.md) — reviews recent changes and refreshes the references. The original skills use the ShipTest source repository and ChatGPT knowledge-base documents.
- [Refine a story](.agents/skills/refine/SKILL.md) — reviews a story number, attachment, or file path and returns short tables of risks and open questions.
- [Local database](.agents/skills/db-local/SKILL.md) — answers questions about ShipTest records using read-only SQLite queries.
- [Functional Test](.agents/skills/functional-test/SKILL.md) — generates manual UI test cases in the ShipTest Excel format.
- [Test Execution](.agents/skills/test-execution/SKILL.md) — runs browser scenarios and records results and screenshots in the Excel workbook.
