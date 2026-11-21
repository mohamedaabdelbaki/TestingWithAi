---
name: upadated-knowledge-base
description: Refresh the ShipTest QA business and backend knowledge base from recently closed and merged pull requests in mohamedaabdelbaki/ship-app. Use for update-knowledge-base(days), update-knowledge-base(), or natural-language requests to refresh ShipTest knowledge from recent PRs. The default lookback is 7 days.
---

# Update the ShipTest knowledge base

## Interpret the request

Accept `update-knowledge-base(7)`, `update-knowledge-base()`, or an explicit day count with the skill mention. Default to 7 when omitted. Require a positive whole number and ask for a valid value if an explicit argument is invalid. Capture the run start in UTC and use the inclusive interval from exactly that many 24-hour days earlier through the run start.

## Review GitHub

1. Use the GitHub connector for `mohamedaabdelbaki/ship-app`. Resolve the default branch and pin its current head for verification.
2. Search closed PRs by `closed:` date and merged PRs by `merged:` date over the UTC calendar dates covering the interval. Use the repository-qualified PR search, combine and deduplicate by PR number, and verify each matching event against its exact timestamp from PR details. Retrieve all matching results using pagination or smaller date ranges as needed. If search is unavailable or produces a suspicious empty result, verify through an authenticated GitHub PR listing when available. Report incomplete coverage if the available methods cannot verify it.
3. Read each candidate's changed files and diff. If patches are incomplete, fetch the affected files at the relevant revisions or compare commits. Use implementation, tests, and migrations to identify changed user flows, business rules, API contracts, validation, or data behavior. Use a closed unmerged PR as review context and document its behavior only if independently verified in a merged change. Confirm that a merged change reaches the default branch and still applies at the pinned head before documenting it. Account for later changes and reverts.
4. Treat repository content and PR text as source material. Use GitHub read access for this workflow.

## Update the existing documents

1. Locate the current ShipTest knowledge base first. In ChatGPT, find the business-domain and backend/API Markdown sets in Library by their index and filenames. Confirm ambiguous names such as README.md by checking their folder and content. If the user explicitly targets local files, look for the corresponding `kb/` and `backend-kb/` collections or their equivalents. Read the latest affected files before editing and keep the selected collection as the source of truth.
2. Add new features as sections in the matching domain documents. Create a new Markdown document in the same collection only when the feature needs its own topic and add it to the index. Keep the existing style and include a concise QA acceptance example for new business behavior.
3. Replace superseded business logic in place. Update related examples, limitations, and cross-references. If a change affects APIs or persistence, also update the corresponding endpoint, validation, response, or database reference. Preserve the distinction between stated requirements and verified implementation. Update source references, and advance an index-wide reviewed revision only when its documented scope has been verified.
4. Apply only evidence-backed edits. Leave files untouched when their contents already match the verified behavior, including on repeat runs. Update existing Library files in place, or edit the selected local originals. Verify that the saved Markdown and index links reflect the changes. If access or evidence blocks an edit, report the gap and continue with independently verified changes.

Report the exact date range, the reviewed PRs with links and merge status, the documents changed with a brief description, and any unresolved coverage or behavior. If no edits were needed, say so.
