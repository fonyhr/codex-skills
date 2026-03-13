---
name: fcs-writing-jira-analysis
description: Use when turning an existing fcs-writing-plans markdown plan into a short Jira analysis summary for a feature or bug.
---
# Writing Jira analysis

## Overview
Create a short, non-implementation analysis document for Jira based on one or more existing plans, written for technically literate non-developers.

## When to use
- You have a plan file produced by `fcs-writing-plans` and need a Jira-ready analysis summary.
- The output should guide future brainstorming and help stakeholders understand scope and intent.

## When not to use
- You need an implementation plan, detailed design, or execution steps.
- There is no plan file to base the analysis on.

## Quick start
1. Ask which plan files in `docs/plan/` should be included.
2. Draft a short analysis in `docs/analysis/` with max two paragraphs and at most one UL list.
3. Name the file `{dd-mm-yyyy}-{kebab-case-name}-analysis.md` and reference it in the response.

## Procedure
1. Ask which plan files should be included; if unclear, ask 1-2 questions before writing.
2. Summarize the goal and scope in the first paragraph using plain technical language.
3. Use a single UL list for the key items (e.g., main changes, risks, or verification focus).
4. Close with a second paragraph that frames impact and dependencies; do not describe implementation.
5. Save to `docs/analysis/` and stop after writing; ask whether to proceed or adjust.

## Common mistakes
- Copying step-by-step implementation details from the plan.
- Writing more than two paragraphs or multiple lists.
- Using jargon that a non-developer cannot follow.
- Skipping file naming and location rules.

## Quality checks
- `docs/analysis/` exists; file name matches `{dd-mm-yyyy}-{kebab-case-name}-analysis.md`.
- The analysis has max two paragraphs and at most one UL list.
- The tone is technical but accessible, and avoids implementation details.
