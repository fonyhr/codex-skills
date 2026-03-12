---
name: fcs-brainstorming
description: Use before any creative work that creates features, builds components, adds functionality, or changes behavior; explore user intent, requirements, and design before implementation.
metadata:
  short-description: Application design brainstorming
---
# Application brainstorming

## Purpose
Turn ideas into a clear application design and scope before any implementation.

## Non-negotiables
- Do not write code or make changes before a design is presented and approved.
- Ask only one question per message.
- Prefer multiple-choice questions when possible.
- Always propose 2-3 approaches with tradeoffs and a recommendation.
- Keep output in Czech per language rules.
- Hard stop after design approval: do not proceed to planning or implementation until the user explicitly approves switching to fcs-writing-plans.

## Checklist (in order)
1. Explore current project context (files, docs, recent changes).
   - If the project uses Vue 3, load and follow the `vue-best-practices` skill.
   - If the project uses React 19, load and follow the `react-best-practices` skill.
2. Clarify goals and constraints (platform, framework, build, runtime).
3. Ask clarifying questions one at a time.
4. Propose 2-3 approaches with tradeoffs and your recommendation.
5. Present the design in sections scaled to complexity.
6. Ask for approval after each section.
7. Transition to `fcs-writing-plans` only after approval (the plan must be written to `docs/plan/`).

## Process flow
```dot
digraph fcs_brainstorming {
  "Explore project context" [shape=box];
  "Clarify goals and constraints" [shape=box];
  "Ask clarifying questions" [shape=box];
  "Propose 2-3 approaches" [shape=box];
  "Present design sections" [shape=box];
  "User approves design?" [shape=diamond];
  "Invoke fcs-writing-plans\n(write plan to docs/plan/)" [shape=doublecircle];

  "Explore project context" -> "Clarify goals and constraints";
  "Clarify goals and constraints" -> "Ask clarifying questions";
  "Ask clarifying questions" -> "Propose 2-3 approaches";
  "Propose 2-3 approaches" -> "Present design sections";
  "Present design sections" -> "User approves design?";
  "User approves design?" -> "Present design sections" [label="no, revise"];
  "User approves design?" -> "Invoke fcs-writing-plans\n(write plan to docs/plan/)" [label="yes"];
}
```

**Terminal state: invoke `fcs-writing-plans`.**
**Stop condition:** After the user approves the design, ask for explicit permission to switch to `fcs-writing-plans` and wait. Do not continue in the same turn.

## Process guidance
### Understanding the idea
- If the request spans multiple subsystems, surface it and decompose first.
- For appropriately scoped work, focus on purpose, constraints, success criteria.
- Keep scope tight; remove unnecessary features (YAGNI).

### Exploring approaches
- Lead with the recommended option and why.
- Compare complexity, risks, time, maintenance, and compatibility with the stack.

### Presenting the design
- Cover architecture, components, data flow, error handling, and testing.
- Keep each section short unless complexity requires more detail.
- Validate after each section and revise if needed.

### Design for clarity
- Define clear boundaries between modules.
- Ensure each unit has a single purpose and a well-defined interface.
- Avoid tangling responsibilities; keep files focused.

## Language
- Respond in Czech per the `communication-standard` skill.
