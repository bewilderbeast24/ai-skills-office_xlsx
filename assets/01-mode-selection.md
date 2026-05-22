# Step: 01-mode-selection

## Description
This stage determines the operational mode for `xlsx-processing` based on the user's requirements.

## Purpose
- Identify whether the user needs to read/analyze, create, or edit a spreadsheet.
- Select the appropriate mode to ensure correct guidelines are loaded.

## Pre-stage Checkpoint
- Ensure `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` is initialized based on `[checklist.md](../references/checklist.md)`.

### Version Control
- Execute `git status` to ensure a clean working tree before proceeding if applicable.

## Workflow

### Process
1. Analyze the user's prompt to determine the goal.
2. Select one of the following modes:
   - *read-analyze*: For data analysis, visualization, text extraction or basic Pandas operations.
   - *create-spreadsheet*: For creating a new workbook from scratch.
   - *edit-spreadsheet*: For editing an existing workbook, adding columns, or updating templates.
3. Save the selected mode into the internal state.

### Output Format
- Selected Mode Name stored in memory.

## Post-stage Checkpoint

### Progress Tracking
- Update `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` by marking Phase 1: Mode Selection as complete.

### Version Control
- N/A

### Human in the Loop (HITL)
- Ask for user confirmation on the selected mode if there is ambiguity.

### Auto pilot
- If the intent is clear from the prompt (e.g., "create a new spreadsheet"), automatically proceed to Stage 2.
