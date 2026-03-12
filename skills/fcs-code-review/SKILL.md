---
name: fcs-code-review
description: Use when the user requests a senior review of the full diff between the current branch and a target branch across all changed files (code, configs, docs), producing a Markdown report for GitLab MR threads.
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
   - Identify the primary language(s) and any framework(s) used by the change (e.g., React, Vue, Angular, Next.js).
   - If the project uses Vue, load and follow the `vue-best-practices` skill.
   - Check functional correctness and edge cases.
   - Check the surrounding context of the diff hunk for regressions (e.g., changed assumptions, broken flows, unintended side effects).
   - Scan nearby files/modules that interact with the change (imports, shared utilities, type defs, config/CI pipelines) for compatibility.
   - Check efficiency and alternative implementations. Consider whether the diff can be solved more simply or with lower cost.
   - Check project conventions and consistency with existing code.
   - Check maintainability, readability, and API design.
   - Check static types or contracts when applicable (correctness, unsafe casts, any usage).
   - Check linting and formatting inconsistencies.
   - Search for similar solutions already present in the project and note opportunities to reuse, merge, or replace the new code.
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
- <nález nebo "Nenalezeny žádné problémy.">

## Nice-to-have
- <nález nebo "Nenalezeny žádné problémy.">

## Lint/Format
- <nález nebo "Nenalezeny žádné problémy.">

## Types/Static analysis
- <nález nebo "Nenalezeny žádné problémy.">

## Maintainability
- <nález nebo "Nenalezeny žádné problémy.">

## Performance
- <nález nebo "Nenalezeny žádné problémy.">

## Security
- <nález nebo "Nenalezeny žádné problémy.">
```

## Language
- Respond in Czech per the `communication-standard` skill.
- Keep the review template headings in English.
- Findings inside the review template must be in Czech.

## Common mistakes
- Skipping the context request and reviewing without intended behavior.
- Mixing categories or leaving findings unclassified.
- Writing long paragraphs instead of short bullets.
- Failing to look for existing implementations that could be reused or merged.

## Quality checks
- The target branch was confirmed or explicitly provided.
- Context was requested and recorded.
- Findings are categorized and concise.
- The report is saved under `code-review/` as Markdown.
