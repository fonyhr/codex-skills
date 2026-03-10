---
name: js-executing-plans
description: Execute approved JavaScript/TypeScript implementation plans with batch checkpoints and strict adherence to plan steps. Use when a written plan is approved and must be executed in a separate session with review checkpoints.
---
# JS executing plans

## Overview
Load plan, review critically, execute tasks in batches, report for review between batches.

**Core principle:** Batch execution with checkpoints for review.

**Announce at start:** "I'm using the js-executing-plans skill to implement this plan."

## Rules
- Stick to the approved plan unless the user says otherwise.
- If deviating, explain why and propose a plan update.
- After each step, state what changed.
- Do not start implementation on main/master without explicit user consent.

## Process
### Step 1: Load and Review Plan
1. Read plan file or user-provided plan text.
2. Review critically and identify questions or concerns.
3. If concerns: raise them before starting.
4. If no concerns: create a task list and proceed.

### Step 2: Execute Batch
**Default: First 3 tasks**

For each task:
1. Mark as in_progress.
2. Follow each step exactly.
3. Run verifications as specified.
4. Mark as completed.

### Step 3: Report
When batch complete:
- Show what was implemented.
- Show verification output (summarize if long).
- Say: "Ready for feedback."

### Step 4: Continue
Based on feedback:
- Apply changes if needed.
- Execute next batch.
- Repeat until complete.

### Step 5: Complete Development
After all tasks complete and verified:
- Summarize impact.
- Propose quick verification.

## When to Stop and Ask for Help
Stop executing immediately when:
- Hit a blocker mid-batch (missing dependency, test fails, instruction unclear).
- Plan has critical gaps preventing starting.
- You don't understand an instruction.
- Verification fails repeatedly.

Ask for clarification rather than guessing.

## When to Revisit Earlier Steps
Return to review (Step 1) when:
- User updates the plan based on your feedback.
- Fundamental approach needs rethinking.

Do not force through blockers. Stop and ask.

## Verification
- At the end, summarize impact and propose quick verification.

## Language
- Respond in Czech per the `czech-communication-standard` skill.
