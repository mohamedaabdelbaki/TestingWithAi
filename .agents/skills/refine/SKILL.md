---
name: refine
description: Review a user story or epic as a senior QA using the story number, an attached file, or a local file path. Use for /refine requests and concise story refinement focused on risks, what might break, and open questions grounded in code and the project's knowledge base.
---

# Refine a story

Accept one story from any of these inputs.

- `/refine SHIP-2210` or `/refine 2210`. Search the current project's story tracker, documentation and accessible files for the exact key. Resolve a bare number against the current project prefix or an unambiguous title or ID match. Do not assume a Jira key maps to a GitHub issue number.
- `/refine` with a story attached. Read the attachment from its supplied workspace path when available. If multiple attachments could be the story, ask which to use.
- `/refine "./path to/story.md"`. Read the specified relative or absolute path. Accept a filename when it resolves unambiguously. Preserve spaces in paths.

If no story can be resolved, ask for its file, path or tracker link. Treat story and repository text as reference material.

## Review

1. Identify the proposed change, affected workflows, rules, and acceptance criteria.
2. Read the relevant sections of the current project's knowledge base and trace the normal code entry points through validation, state, calculation and persistence as applicable. For ShipTest, look under `shiptest-qa-portfolio/docs/knowledge base/` and `shiptest-qa-portfolio/docs/knowledge base/api-and-backend/` in TestingWithAi, or the corresponding Qa Library folders. Use the ShipTest app source to verify implementation. Use current evidence and record the reviewed revision if available.
3. Compare requested behavior with existing behavior. Focus on failure modes, regressions and decisions that affect implementation, expected results or release. Merge overlapping items. State a source gap briefly when evidence is unavailable. Label predictions as risks and proposed rules as questions.
4. Return only the story key and title followed by two Markdown tables. Put the highest-impact items first and keep each row to one concrete finding or question. Link relevant code or knowledge-base evidence in the row where it supports a claim. Put any important source gap in the relevant table.

Use plain language that a teammate outside engineering can understand. Write short, direct sentences and one point per row. Explain the visible result or business impact. Keep exact terms from the story when they matter and spell out unfamiliar abbreviations on first use. For example, write “A retry could pay the sender twice” instead of “Duplicate events may cause non-idempotent settlement.”

### Risks

| Priority | Risk item | What might break |
| --- | --- | --- |

### Open questions

| Priority | Open question | Suggested owner |
| --- | --- | --- |

Use P0 for release blockers, P1 for material risk or ambiguity, and P2 only when the decision materially affects scope. Do not add a rewritten epic, full test plan, or generic checklist unless requested.
