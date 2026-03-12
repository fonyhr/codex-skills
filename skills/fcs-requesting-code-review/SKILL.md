---
name: fcs-requesting-code-review
description: Use after implementation to review the full diff against a target branch and directly fix any findings instead of producing a report.
---
# Requesting code review (auto-fix)

## Overview
Review the full diff against a target branch, identify issues, and fix them directly in the working tree.

## When to use
- After implementation is complete and you need a senior-level review that results in fixes, not a report.

## When not to use
- When the user explicitly wants a written review report.
- When changes are incomplete or still in flux.

## Quick start
1. Ask for the target branch if missing.
2. Ask for context: goal of the change, intended behavior, constraints, and testing notes.
3. Review the full diff against the target branch.
4. Fix any findings directly in code, configs, or docs.
5. Summarize changes and verification.

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
   - If the project uses Vue 3, load and follow the `vue-best-practices` skill.
   - If the project uses React 19, load and follow the `react-best-practices` skill.
   - Check functional correctness and edge cases.
   - Check the surrounding context of the diff hunk for regressions (e.g., changed assumptions, broken flows, unintended side effects).
   - Scan nearby files/modules that interact with the change (imports, shared utilities, type defs, config/CI pipelines) for compatibility.
   - Check efficiency and alternative implementations. Consider whether the diff can be solved more simply or with lower cost.
   - Check project conventions and consistency with existing code.
   - Check maintainability, readability, and API design.
   - Check static types or contracts when applicable (correctness, unsafe casts, any usage).
   - Check linting and formatting inconsistencies.
   - Search for similar solutions already present in the project and note opportunities to reuse, merge, or replace the new code.
4. Fix findings directly:
   - Apply fixes in the working tree and keep changes scoped to the issue.
   - If a fix is uncertain, stop and ask the user before changing behavior.
   - Avoid large refactors unless required to resolve a defect.
5. Verification:
   - Run any relevant tests if feasible.
   - If tests are too heavy or unavailable, state what was not run.
6. Report back:
   - Summarize the fixes applied.
   - Summarize verification results.
   - Explicitly state that no review report was created.

## Common mistakes
- Writing a review report instead of fixing issues.
- Skipping the context request and reviewing without intended behavior.
- Making broad refactors without a clear defect.
- Fixing code while understanding is incomplete.

## Quality checks
- Target branch confirmed.
- Context captured.
- All meaningful findings fixed or explicitly deferred with user approval.
- No `code-review` Markdown report created.

## Language
- Respond in Czech per the `communication-standard` skill.
