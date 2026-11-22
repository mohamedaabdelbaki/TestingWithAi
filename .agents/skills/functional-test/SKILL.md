---
name: functional-test
description: Create manual functional UI test cases for business rules from a feature, workflow, story ID, attachment, or file path. Use for /functional-test requests and ShipTest test design grounded in the project knowledge base.
---

# Design functional UI test cases

1. Use the requested feature, workflow or rule as scope. For a story ID, resolve the exact key through the current tracker or project files. Read a supplied attachment or path directly. If the story cannot be found, ask for its file or tracker link.
2. Read the relevant business knowledge base first. For ShipTest use ChatGPT's `/Qa/knowledge base` or the [TestingWithAi knowledge base](https://github.com/mohamedaabdelbaki/TestingWithAi/blob/main/shiptest-qa-portfolio/docs/knowledge%20base/README.md). Use its frontend reference for page names, controls and navigation. Verify business rules and UI steps against current evidence when needed. Keep the documented expectation distinct from any observed behavior.
3. Design manual tests through the UI only. Cover representative valid and invalid inputs, meaningful boundaries, rule combinations and state changes. Include pricing calculations and known boundary values when relevant. Use API and backend references only to clarify a business rule if necessary. Omit API, database, performance and other non-functional test steps.
4. Use simple wording and the actual UI labels. Put shared accounts, fixtures and setup on the Test Data and Notes sheet. Every row must have a unique ID and enough information to run independently, or an explicit prerequisite. Use synthetic data and make expected results visible and specific.
5. Use a **Needs clarification** section for unresolved or contradictory rules. Do not set a final pass criterion from an unconfirmed decision. Set new cases to Pending and leave Actual Result and BUG_ID blank. Record observed outcomes only when execution was separately requested and completed.

## Excel output

By default, deliver an editable .xlsx modeled on the [ShipTest workbook](https://chatgpt.com/library?file_id=libfile_5e1ab6d8a9f48191a835248152058a8b&account_id=personal). Inspect the current template when accessible and use the project-specific content and case count. Use a different output format when explicitly requested.

### ShipTest Test Execution

- Use a navy title and column headers, teal scenario bands, alternating white and pale blue case rows, and amber Pending cells. Wrap and top-align case text, size rows for the contents, hide gridlines, and freeze the header area.
- Include prominent Pass, Fail, Pending and total case counts above the table. Use formulas over the generated case area, excluding scenario headings. Verify the initial pending and total counts match the case count.
- Group cases under labeled test scenarios. Keep numbered steps on separate lines within the Test Steps cell. Include the business rule in the description when identifiable.

| ID | Test Case Description | Pre Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | BUG_ID |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

### Test Data and Notes

- Match the navy title, teal section headings, light information panels and alternating table rows.
- Organize applicable content under Test environment and accounts, Receiver test data, Shared parcel data and execution notes, and Needs clarification. Adapt fixture names to the feature. Keep identifiers and phone numbers as text when leading zeros matter.
- Link to the relevant knowledge base. Before delivery, check unique case IDs, complete steps and expectations, summary totals, and readable row heights.

Defect severity and fix priority are recorded only for observed product defects during execution. Leave them out of the generated test suite.
