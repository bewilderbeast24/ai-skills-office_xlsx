# Step: 02-context-setup

## Description
This stage loads the required standards and identifies the target files for the operation.

## Purpose
- Load formatting and development guidelines.
- Identify the target file paths.

## Pre-stage Checkpoint
- The operational mode MUST be clearly defined from Step 01.

### Version Control
- N/A

## Workflow

### Process
1. Read `[formatting-standards.md](../references/formatting-standards.md)` to understand rules for color coding, formula construction, and numerical formatting.
2. Read `[development-guidelines.md](../references/development-guidelines.md)` to understand requirements for using openpyxl vs pandas and formula verification.
3. Identify the target input file(s) or specify the output filename.

### Output Format
- Target paths identified.

## Post-stage Checkpoint

### Progress Tracking
- Update `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` by marking Context Setup as complete.

### Version Control
- N/A

### Human in the Loop (HITL)
- If the target file path is ambiguous, explicitly ask the user for clarification.

### Auto pilot
- If target files are provided or a clear path is established, proceed to the corresponding Specialized Workflow (Stage 3).
