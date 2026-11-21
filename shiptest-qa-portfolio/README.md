# ShipTest QA Portfolio

A software testing portfolio for a shipping application. The project translates application behavior and user stories into testable business rules, documents API and database contracts, and demonstrates AI-assisted incident triage using simulated service logs.

| Explore | What it contains |
| --- | --- |
| [Business requirements](docs/requirements/ship-app-business-requirements.html) | HTML report covering the shipment workflow, validation, pricing and management. Download and open in a browser. |
| [Business knowledge base](docs/business/README.md) | Eight functional domains with rule summaries, acceptance examples and implementation differences to investigate. |
| [API and database reference](docs/api/README.md) | 19 API paths and 22 method/path combinations, with request and response examples, database effects and Postman setup notes. |
| [Incident investigation](docs/incidents/shipment-incident-qa-practice.md) | AI-assisted practice exercise tracing a simulated shipment booking failure across service logs. |
| [Incident dashboard](docs/incidents/shipment-incident-dashboard.html) | Evidence, timeline, failure ownership and payment impact for the simulation. Download and open in a browser. |

## QA approach

- Compare user stories with the implemented rules for contacts, route eligibility, services, pickup, options, pricing and shipment lifecycle.
- Use the API contracts to design positive, negative and boundary checks. Compare results with expected state changes in SQLite.
- Trace simulated service events by request ID and record what the evidence supports, what remains uncertain and who should investigate the fix.

## Scope and evidence

This portfolio documents requirements analysis, source review and a simulated incident investigation. The API examples use synthetic data and are derived from source. Test scenarios are design examples. No live test run or automated test suite is included in this snapshot.

[ShipTest](https://github.com/mohamedaabdelbaki/ship-app/tree/447c72c4b4eca87f1b4906052eecb4fdd8bd6373) is the training application reviewed for this project. Credit for the application belongs to its original contributors. Follow the application repository’s setup instructions to run it locally.

## CV entry

**ShipTest QA Portfolio**  
Analyzed eight shipping business domains, documented 22 API method and path combinations and their database effects, and created an AI-assisted incident dashboard for a simulated shipment booking failure.
