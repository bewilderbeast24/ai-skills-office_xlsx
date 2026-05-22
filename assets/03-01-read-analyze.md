# Step: 03-01-read-analyze

## Description
Specialized workflow for analyzing data within an existing Excel file.

## Purpose
- Extract insights, calculate statistics, or perform data manipulations using Pandas.

## Pre-stage Checkpoint
- Target files MUST exist and be accessible.

### Version Control
- N/A

## Workflow

### Process
1. Use `pandas` to read the Excel file (e.g., `pd.read_excel('file.xlsx')`).
2. Specify data types when reading to avoid inference issues if necessary.
3. Perform the requested analysis, formatting, or extraction operations.
4. If outputting a summary, ensure the data is presented clearly.

### Output Format
- Summary statistics, markdown tables, or a transformed dataset.

## Post-stage Checkpoint

### Progress Tracking
- Update `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` by marking Specialized Workflow Execution as complete.

### Version Control
- N/A

### Human in the Loop (HITL)
- If the analysis returns unexpected results, query the user for next steps.

### Auto pilot
- Complete the analysis and proceed to Outcome (Stage 4).
