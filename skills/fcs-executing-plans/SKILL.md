---
name: fcs-executing-plans
description: Use when a written implementation plan is approved and must be executed with batch checkpoints and strict adherence to plan steps, in a separate session with review checkpoints.
metadata:
  short-description: Execute plans
---
# Executing plans

## Overview
Load plan, review critically, execute tasks in batches, report for review between batches.

**Core principle:** Batch execution with checkpoints for review.

**Announce at start:** "I'm using the fcs-executing-plans skill to implement this plan."

## Rules
- Stick to the approved plan unless the user says otherwise.
- If deviating, explain why and propose a plan update.
- After each step, state what changed.
- Do not start implementation on main/master without explicit user consent.
- Do not begin until the user provides the plan name (or full path) to implement.
- The plan must exist under docs/plan/ unless the user explicitly provides a different location.

## Process
### Step 1: Load and Review Plan
1. Ask for the plan name to implement (prefer a file in docs/plan/).
2. Verify the plan file exists; if not, ask for the correct name/path.
3. Read the plan file or user-provided plan text.
4. Review critically and identify questions or concerns.
5. If concerns: raise them before starting.
6. If no concerns: create a task list and proceed.

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
- Respond in Czech per the `communication-standard` skill.
