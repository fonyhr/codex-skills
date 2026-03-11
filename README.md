# Codex Skills

This repository contains Codex skills packaged for installation into the JetBrains AI Chat plugin using the Codex agent.

## Repository URL

```
https://github.com/fonyhr/codex-skills
```

## Structure

Each skill lives under `skills/<skill-name>/SKILL.md` and must contain a YAML front-matter header with `name` and `description`.

Example:

```yaml
---
name: my-skill
description: Short description of what the skill does
---
```

## Install a skill from this repo

Use the Codex skill installer:

```bash
scripts/install-skill-from-github.py --repo fonyhr/codex-skills --path skills/<skill-name>
```

Install multiple skills in one command:

```bash
scripts/install-skill-from-github.py --repo fonyhr/codex-skills --path skills/communication-standard skills/js-brainstorming skills/js-executing-plans
```

After installation, restart Codex to pick up new skills.
