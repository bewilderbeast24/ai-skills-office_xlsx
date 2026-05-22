# Step: 03-02-create-spreadsheet

## Description
Specialized workflow for generating a completely new `.xlsx` file.

## Purpose
- Generate robust Excel workbooks with formulas instead of hardcodes.

## Pre-stage Checkpoint
- `[formatting-standards.md](../references/formatting-standards.md)` MUST be fully understood and applied here.

### Version Control
- N/A

## Workflow

### Process
1. Use `openpyxl` to create a new `Workbook()`.
2. Apply industry-standard color conventions (Blue for inputs, Black for formulas) if creating a financial model.
3. Inject dynamic Excel formulas instead of calculating values in Python and hardcoding the result.
4. Format cells appropriately (currency, percentages, text alignment).
5. Add documentation/comments for any assumptions or hardcoded inputs.
6. Save the workbook to the requested destination path.

### Output Format
- A new `.xlsx` file at the specified directory.

## Post-stage Checkpoint

### Progress Tracking
- Update `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` by marking Specialized Workflow Execution as complete.

### Version Control
- N/A

### Human in the Loop (HITL)
- Wait for user feedback if design decisions (like color scheme or formatting) are unstated.

### Auto pilot
- Build the workbook following best practices and proceed to Outcome (Stage 4).
