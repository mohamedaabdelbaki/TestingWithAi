---
name: check-severity-priority
description: Classify defects found during test execution. Use for /check-severity-priority or /check-severity&priority to record severity and suggested priority from observed test results.
---

# Check severity and priority

Apply only when test execution reveals a product defect. Compare the expected and actual results. Omit severity and priority from test design and from passed, unrun, skipped or blocked cases. If the result could be caused by setup, test data or an unclear expectation, record what needs verification before classifying it.

## Severity

Assess technical impact within the affected scope. QA typically assesses severity.

| Level | Impact |
| --- | --- |
| Blocker (Showstopper) | The app is unusable in the affected environment. |
| Critical | A core feature or workflow fails. |
| Major | The feature works but produces materially wrong results or has a substantial issue. |
| Medium (Average) | Part of the functionality is affected and the main task remains possible. |
| Minor (Low) | The issue has limited impact, such as unclear wording. |
| Trivial | The issue is purely cosmetic. |

## Priority

Assess urgency separately using customer impact, frequency, workarounds, revenue, trust and release timing. QA suggests priority. Product, the team lead or the business owner typically confirms it.

| Level | Urgency |
| --- | --- |
| High | Fix immediately because of material customer or business impact or a near-term release need. |
| Medium | Fix soon. The work can be scheduled. |
| Low | Fix later because the issue has limited urgency. |
| Pending triage | Business context is insufficient. State what needs confirmation. |

A crash on an unsupported browser can be Blocker in that environment and Low priority. A typo on a main checkout button can be Minor and High when it materially affects customer trust.

Add one row per observed defect, using short reasons grounded in the execution evidence.

| Test case | Expected result | Actual result | Severity and impact | Suggested priority and urgency |
| --- | --- | --- | --- | --- |

Source: Difference Between Priority and Severity (2).pdf.
