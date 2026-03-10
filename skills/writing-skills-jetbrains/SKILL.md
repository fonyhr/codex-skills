---
name: writing-skills-jetbrains
description: Create and update Codex skills for the JetBrains AI Chat plugin. Use when the user wants a new skill, edits an existing skill, designs skill structure, writes or improves SKILL.md, creates resources (scripts/references/assets), or needs naming, trigger, and validation guidance.
---
# Writing skills for JetBrains Codex

## Goal
Create a high-quality, detailed, and usable skill for a Codex agent in the JetBrains AI Chat plugin, with clear rules, steps, and templates.

## Quick start
1. Clarify the skill purpose and 3-5 typical requests that should trigger it.
2. Propose structure and any resources (scripts, references, assets).
3. Create the skill folder and write SKILL.md using the template.
4. Check quality and consistency (frontmatter, naming, clear steps).

## Intake questions
- Which specific requests or phrases should trigger the skill?
- Should the skill create or use scripts, references, or assets?
- What is the target output and level of detail?

## Skill structure
Each skill is a folder with a required `SKILL.md`. Add optional folders only when needed.

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
- Prefer short, action-oriented names, e.g. `writing-skills-jetbrains`.

## Frontmatter rules
- `name`: exact skill name.
- `description`: the primary trigger. Describe what the skill does and when to use it.
- Do not add extra fields.

## SKILL.md template
```markdown
---
name: example-skill
description: One-sentence description of what the skill does and when to use it, including triggers.
---
# Skill title

## Goal
One sentence with a clear purpose.

## Quick start
1. ...
2. ...
3. ...

## Intake questions
- ...
- ...

## Procedure
1. ...
2. ...
3. ...

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
- `description` clearly describes when to use the skill.
- The procedure is understandable without additional files.
- No extra files beyond SKILL.md.

## Done
After creating the skill, ask whether the user wants to add resources or refine the triggers in `description`.
