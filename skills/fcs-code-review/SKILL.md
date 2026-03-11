---
name: fcs-code-review
description: Use when the user asks for a senior code review of the full diff between the current branch and a target branch across all changed files (code, configs, docs), with a Markdown report for GitLab MR threads.
metadata:
  short-description: Diff code review
---
# Code review

## Overview
Provide a senior-level review of all changes in an application project by comparing the current branch against a target branch diff and producing a structured Markdown report.
Answer in Czech per the communication-standard skill. Keep the report template headings in English, but write the concrete findings in Czech.

## Quick start
1. Ask for the target branch if it is not provided.
2. Ask for context: goal of the change, intended behavior, constraints, and testing notes.
3. Compare the diff between the current branch and the target branch and identify meaningful changes across the entire change set.
4. Review for correctness, efficiency, conventions, and code similarity to existing project style.
5. If uncertain about behavior, pause and ask for clarification before continuing.
6. Write a Markdown report into the `code-review` folder.

## Procedure
1. Gather required inputs:
   - Ask for the target branch name if missing.
   - Ask for context (Jira issue text or a short description of intended outcome).
   - Ask for constraints (deadlines, backward compatibility, performance budgets).
2. Compute the change set:
   - Compare the diff between the current branch and the target branch to see all changes (e.g., `git diff <target>...HEAD`).
   - Review the full diff (entire change set), not the whole repository.
3. Review the changes across all modified files (code, configs, docs, data files):
   - Check functional correctness and edge cases.
   - Check the surrounding context of the diff hunk for regressions (e.g., changed assumptions, broken flows, unintended side effects).
   - Scan nearby files/modules that interact with the change (imports, shared utilities, type defs, config/CI pipelines) for compatibility.
   - Check efficiency and alternative implementations.
   - Check project conventions and consistency with existing code.
   - Check maintainability, readability, and API design.
   - Check static types or contracts when applicable (correctness, unsafe casts, any usage).
   - Check linting and formatting inconsistencies.
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

## Lint/Format
- <finding or "No issues found.">

## Types/Static analysis
- <finding or "No issues found.">

## Maintainability
- <finding or "No issues found.">

## Performance
- <finding or "No issues found.">

## Security
- <finding or "No issues found.">
```

## Language
- Respond in Czech per the `czech-communication-standard` skill.

## Common mistakes
- Skipping the context request and reviewing without intended behavior.
- Mixing categories or leaving findings unclassified.
- Writing long paragraphs instead of short bullets.

## Quality checks
- The target branch was confirmed or explicitly provided.
- Context was requested and recorded.
- Findings are categorized and concise.
- The report is saved under `code-review/` as Markdown.
