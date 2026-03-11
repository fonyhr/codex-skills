---
name: js-verification-before-completion
description: Use when verifying correctness of JS/TS changes before closing a task, to confirm the solution works.
metadata:
  short-description: JS/TS verification checklist
---
# JS verification before completion

## Checklist
- Is the implementation aligned with the requirement?
- Did tests pass, or is there at least a proposed verification path?
- Did I change API contracts without approval?
- Did I introduce side effects (bundle size, performance)?

## Format
- If verification is not possible, state the concrete reason.
- Propose the shortest path to verification.

## Language
- Respond in Czech per the `czech-communication-standard` skill.
