---
name: test-execution
description: Execute existing functional UI test cases in the browser by scenario number or all scenarios, skipping cases already marked Pass in all mode. Use for /test-execution requests. Default to Scenario 1 and record results and embedded screenshots in the same Excel workbook.
---

# Execute browser test cases

## Select the workbook and cases

- Prefer the workbook supplied or selected by the user. Otherwise use the current project workbook. For ShipTest, look in the Qa Library for the latest `shiptest-functional-test-cases.xlsx`. Use a specified local path when requested. Resolve ambiguous workbook matches before writing.
- Accept `/test-execution` (Scenario 1), `/test-execution 3` or `/test-execution scenario 3`, and `/test-execution all` (remaining cases across all scenarios in workbook order). Read the latest workbook and its setup notes. Use explicit scenario numbers when present. Otherwise count scenario headings from top to bottom, including merged headings such as `Scenario | Register, sign in and see owned shipments`. Domain headings do not count. If the supplied number is unavailable, list the valid numbers and titles.
- In `all` mode, read the current Status before selecting cases and skip any case marked Pass, ignoring capitalization and surrounding whitespace. Run the remaining cases, including Pending, Fail, Blocked, and blank statuses. Preserve the skipped rows and their evidence. If every case already passed, report that there are no remaining cases and finish without editing the workbook.
- When the user explicitly requests a full rerun, include passed cases. A single-scenario run (including the default Scenario 1) reruns all cases in that scenario. Keep the case IDs, steps, test data, expectations, and other scenarios' results as written.

## Execute in the browser

1. Connect to the browser the user is using and verify the intended app, origin, and test environment. Read the case preconditions and prepare authorized synthetic fixtures. Use the project frontend reference to locate controls and follow the workbook's steps through the UI. Check each result against the expected outcome. Use shared setup when it does not change what a case tests.
2. Mark a case Pass when the expected behavior is observed, Fail when the verified behavior differs, or Blocked when a prerequisite prevents a valid run. Leave unattempted cases Pending. Record the actual observation or blocker in plain language. Continue independent cases if a prerequisite fails. Respect the browser's rules for authorization and credentials, and scope mutations to authorized test fixtures.
3. Capture browser screenshots at meaningful checkpoints. Include evidence for both outcomes of a boundary case when possible. Label each screenshot by case ID and the checkpoint it shows. Keep credentials and unrelated private data out of the images. If evidence cannot be captured or embedded, record the gap and continue the cases that can be run.
4. Apply `check-severity-priority` only to observed product defects. Record severity and suggested fix priority with reasons in the defect notes. Use BUG_ID only when a defect is actually logged or an existing defect ID is verified.

## Update the same Excel workbook

- Write Actual Result and Status to the selected case rows on the execution sheet. Add embedded screenshots to a clearly labeled evidence sheet for each scenario, such as `Scenario 1 Evidence`. On reruns, label the new evidence with the run date and time and preserve earlier screenshots. Keep the workbook's existing layout, styles, notes, formulas, and unrelated evidence.
- Refresh and verify the summary counts. If the workbook only counts Pass, Fail and Pending, account explicitly for any Blocked cases so the totals reconcile. Verify the saved workbook opens and that every captured screenshot is embedded and mapped to its case.
- Save the update to the same workbook identity. For a Library workbook, replace the current version with a concurrency check when available. For an explicit local workbook, update that file. Link the updated workbook and summarize Pass, Fail, Blocked and remaining Pending counts. For an all-mode run, report how many previously passed cases were skipped separately from the new run results. Mention any cases that could not run or evidence that could not be attached.
