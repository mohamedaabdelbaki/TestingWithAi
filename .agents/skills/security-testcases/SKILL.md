---
name: security-testcases
description: Create defensive security verification test cases in the ShipTest Excel format from a feature, story, application source, or security review. Use for /security-testcases, control verification planning, and remediation acceptance checks.
---

# Security test cases

## Select the scope

- Accept a feature, story ID, source path, repository link, or security review. When invoked without arguments in the ShipTest project, cover the controls in the current ShipTest security review.
- Read the relevant business rules and security requirements. For ShipTest, start with the Qa knowledge base or the TestingWithAi ShipTest portfolio. Use the current source revision for implementation facts. Distinguish intended controls, observed source findings, and outcomes from tests that have actually run.
- Group relevant checks by feature or control. For ShipTest, use Authentication and sessions, Shipment ownership and pricing, and Assistant and error handling as applicable. Cover representative normal UI behavior plus defensive source, configuration, or remediation verification. Prefer normal product actions with disposable QA accounts in a test instance. Keep each row focused on one control. Omit exploit payloads, bypass or intrusion procedures, and offensive automation.
- Use clearly stated prerequisites, synthetic data, numbered steps, and an observable expected result. Note the source revision or rule when available. If the intended behavior is unresolved, record it under Needs clarification. Do not turn a known weakness into the expected result.

## Excel output

Use an editable .xlsx by default. Match the [ShipTest security workbook](https://chatgpt.com/library?file_id=libfile_e5df093c6d308191a18c0f1912d80444&account_id=personal). Use a different format if requested.

| ID | Test Case Description | Pre Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | BUG_ID |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

- On the Test Execution sheet, use unique SEC IDs, navy headers, teal scenario bands, alternating rows, and wrapped numbered steps. Add formula-driven Pass, Fail, Pending, Blocked and total counts. Give each case a Status dropdown with automatic colors (green Pass, red Fail, amber Pending, blue Blocked).
- On Test Data and Notes, list the test environment, identify browser versus source or configuration checks, link the source baseline, and include needs-clarification items where applicable.
- Set each generated case to Pending. Leave Actual Result and BUG_ID blank. Record severity and fix priority only when separately requested execution reveals a verified product defect. Verify case IDs, status controls, counts, and readable cells before delivering the workbook.
