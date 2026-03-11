---
name: js-code-review
description: Use when the user asks for a JavaScript/TypeScript code review of changes between the current branch and another branch.
---
# JS code review

## Overview
Provide a senior-level review of JS/TS changes by comparing the current branch against a target branch diff and producing a structured Markdown report.

## When to use
- The user asks for a code review of JS/TS changes.
- The user wants a review output that can be pasted into GitLab merge request threads.

## When not to use
- The user wants implementation or fixes instead of review.
- The request is about a non-JS/TS codebase.

## Quick start
1. Ask for the target branch if it is not provided.
2. Ask for context: goal of the change, intended behavior, constraints, and testing notes.
3. Compare the diff between the current branch and the target branch and identify meaningful changes.
4. Review for correctness, efficiency, conventions, and code similarity to existing project style.
5. If uncertain about behavior, pause and ask for clarification before continuing.
6. Write a Markdown report into the `code-review` folder.

## Procedure
1. Gather required inputs:
   - Target branch name (ask if missing).
   - Context (Jira issue text or a short description of intended outcome).
   - Any constraints (deadlines, backward compatibility, performance budgets).
2. Compute the change set:
   - Compare the diff between the current branch and the target branch to see all changes (e.g., `git diff <target>...HEAD`).
   - Focus on code touched by the change; ignore unrelated files when possible.
3. Review the changes:
   - Functional correctness and edge cases.
   - Efficiency and alternative implementations.
   - Project conventions and consistency with existing code.
   - Maintainability, readability, and API design.
   - Types (TypeScript correctness, unsafe casts, any usage).
   - Linting issues (ESLint) and formatting inconsistencies.
4. If any behavior is unclear:
   - Stop and ask the user for clarification.
   - Resume only after receiving the missing context.
5. Write the review report:
   - Save a Markdown file in `code-review/`.
   - Use clear sections for categories.
   - Keep bullets short so they can be pasted into GitLab MR threads.
   - It is acceptable to report no issues when nothing is found.

## Review output template
```markdown
# Code Review - <short title>

## Context
- Target branch: `<branch>`
- Goal: <summary>

## Functional
- <finding or "No issues found.">

## Nice-to-have
- <finding or "No issues found.">

## ESLint
- <finding or "No issues found.">

## TypeScript
- <finding or "No issues found.">

## Maintainability
- <finding or "No issues found.">

## Performance
- <finding or "No issues found.">

## Security
- <finding or "No issues found.">
```

## Common mistakes
- Skipping the context request and reviewing without intended behavior.
- Mixing categories or leaving findings unclassified.
- Writing long paragraphs instead of short bullets.

## Quality checks
- The target branch was confirmed or explicitly provided.
- Context was requested and recorded.
- Findings are categorized and concise.
- The report is saved under `code-review/` as Markdown.
