# Step: 03-03-edit-spreadsheet

## Description
Specialized workflow for modifying or cleaning an existing `.xlsx` file while safely preserving templates and formulas.

## Purpose
- Add columns, modify data, and adjust formatting without breaking existing functionality.

## Pre-stage Checkpoint
- Target Excel file MUST exist.

### Version Control
- N/A

## Workflow

### Process
1. Load the workbook using `openpyxl` (`load_workbook('existing.xlsx')`). DO NOT use `data_only=True` when editing, to avoid permanently losing formulas.
2. Maintain existing template conventions. They override standard guidelines.
3. Inject new formulas where needed rather than hardcoding calculated values.
4. Perform the required edits (insert/delete rows/columns, change cell values).
5. Save the workbook, potentially to a new file name to avoid overwriting the original if requested.

### Output Format
- An updated `.xlsx` file.

## Post-stage Checkpoint

### Progress Tracking
- Update `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` by marking Specialized Workflow Execution as complete.

### Version Control
- N/A

### Human in the Loop (HITL)
- If existing templates have conflicting patterns with requested edits, verify with the user before proceeding.

### Auto pilot
- Modify the workbook and proceed to Outcome (Stage 4).
