# Step: 04-outcome

## Description
Final verification and delivery of the generated or modified spreadsheet.

## Purpose
- Ensure there are ZERO formula errors and present the results to the user.

## Pre-stage Checkpoint
- The `.xlsx` file MUST be successfully saved to disk.

### Version Control
- N/A

## Workflow

### Process
1. If the operation involved any formulas, execute `python scripts/recalc.py <output_file>`.
2. Analyze the JSON output from `recalc.py`. If the status is `errors_found`, identify the errors (e.g., `#REF!`, `#DIV/0!`), reopen the file, correct the formulas, and re-run the recalculation.
3. Generate a directory tree representation of the final outputs.
4. Deliver the final confirmation to the user.

### Output Format
- Directory tree and final success message.

## Post-stage Checkpoint

### Progress Tracking
- Update `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` by marking Finalization as complete.

### Version Control
- N/A

### Human in the Loop (HITL)
- Provide the final file and wait for user acknowledgment.

### Auto pilot
- Finalize the operation autonomously and end the turn.
