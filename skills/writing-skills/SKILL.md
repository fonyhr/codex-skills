---
name: writing-skills
description: Use when creating, updating, or reviewing Codex skills for the JetBrains AI Chat plugin, especially to define triggers, structure, and supporting resources.
metadata:
  short-description: Create or update skills
---
# Writing skills

## Overview
Writing skills is documentation design for agent behavior. The goal is to capture proven techniques, patterns, and tools so future agents can apply them consistently.

## What is a Skill?
A skill is a reusable reference guide for techniques, patterns, or tools that help an agent solve tasks reliably.

Skills are:
- Reusable techniques, patterns, tools, reference guides.

Skills are not:
- Narratives about a one-off solution.

## Quick start
1. Clarify the skill purpose and 3-5 typical requests that should trigger it.
2. Propose structure and any resources (scripts, references, assets).
3. Create or update the skill folder and write SKILL.md using the structure below.
4. Check quality and consistency (frontmatter, naming, clear steps).

## Intake questions
- Which specific requests or phrases should trigger the skill?
- Should the skill create or use scripts, references, or assets?
- What is the target output and level of detail?

## When to create a skill
Create when:
- The technique is not obvious and requires judgement.
- You would reuse it across tasks or projects.
- The pattern is broadly applicable, not project-specific.
- It prevents recurring errors or rationalizations.

Do not create when:
- It is a one-off solution.
- It is project-specific (put it in the project instructions like `AGENTS.md` or `CLAUDE.md`).
- It is a mechanical constraint that can be enforced by tooling.
- It is already well documented elsewhere and you can link to it.

## Skill types
- Technique: concrete method with steps to follow.
- Pattern: way of thinking about a class of problems.
- Reference: API docs, syntax guides, tool documentation.
- Discipline: rules that enforce a process or guardrails.

## Directory structure
Each skill is a folder with a required `SKILL.md`. Keep the namespace flat and searchable.

Required:
- `SKILL.md` with YAML frontmatter `name` and `description`.

Optional:
- `agents/openai.yaml` only if the project uses UI metadata for skill lists.
- `scripts/` for deterministic actions that repeat often.
- `references/` for long or specialized instructions outside SKILL.md.
- `assets/` for templates, icons, documents, or boilerplate.

Do not add:
- `README.md`, `CHANGELOG.md`, `INSTALLATION_GUIDE.md`, or other auxiliary docs.

## Naming rules
- Use the skill name in both `name` and the folder name.
- Use only lowercase letters, digits, and hyphens.
- Prefer short, action-oriented names, e.g. `writing-skills`.

## Frontmatter rules
- `name`: exact skill name.
- `description`: the primary trigger. Describe when to use it, not what it does.
- Do not add extra fields.
- Start with "Use when..." and keep it short and concrete.

## SKILL.md structure
Use concise sections. Prefer inline content for principles and short patterns. Move heavy reference or tools into separate files.

Recommended sections:
- Overview or Goal (1-2 sentences).
- When to use / When not to use.
- Quick start (3-5 steps).
- Procedure or Core pattern.
- Examples (one strong example beats many weak ones).
- Common mistakes.
- Quality checks.

## SKILL.md template
```markdown
---
name: example-skill
description: Use when [specific triggering conditions and symptoms].
---
# Skill title

## Overview
One sentence with a clear purpose.

## When to use
- ...

## When not to use
- ...

## Quick start
1. ...
2. ...
3. ...

## Procedure
1. ...
2. ...
3. ...

## Common mistakes
- ...

## Quality checks
- ...
- ...
```

## Skill creation procedure
1. Collect requirements and usage examples from the user.
2. Define scope and choose the level of detail.
3. Decide whether `scripts/`, `references/`, or `assets/` are needed.
4. Create the skill folder and SKILL.md.
5. Write SKILL.md in imperative form with clear steps and checks.
6. Manually verify that `description` truly triggers the skill in relevant cases.
7. If the skill enforces discipline or process, test it with a baseline scenario and refine to close loopholes.

## Instruction writing rules
- Use short, unambiguous sentences.
- Avoid generic filler, focus on actionable steps.
- When multiple variants exist, state decision criteria.
- Move long details into `references/`.

## JetBrains AI Chat context
- Work with the local repository and use PowerShell.
- Use `rg` for search and `Get-ChildItem` for listing.
- Use `apply_patch` for edits; do not rewrite full files.
- Use absolute paths when referencing files.

## Quality checks
- `SKILL.md` contains only `name` and `description` in frontmatter.
- `description` clearly describes when to use the skill (trigger-focused).
- The procedure is understandable without additional files.
- No extra files beyond SKILL.md.

## Done
After creating the skill, ask whether the user wants to add resources or refine the triggers in `description`.

## Language
- Respond in Czech per the `communication-standard` skill.
