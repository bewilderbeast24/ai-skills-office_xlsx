---
name: office-xlsx
description: "Use when a spreadsheet file is the primary input or output. This means any task where the user wants to: open, read, edit, or fix an existing .xlsx, .xlsm, .csv, or .tsv file (e.g., adding columns, computing formulas, formatting, charting, cleaning messy data); create a new spreadsheet from scratch or from other data sources; or convert between tabular file formats. Trigger especially when the user references a spreadsheet file by name or path — even casually (like \"the xlsx in my downloads\") — and wants something done to it or produced from it. Also trigger for cleaning or restructuring messy tabular data files (malformed rows, misplaced headers, junk data) into proper spreadsheets. The deliverable must be a spreadsheet file. Do NOT trigger when the primary deliverable is a Word document, HTML report, standalone Python script, database pipeline, or Google Sheets API integration, even if tabular data is involved."
---

# xlsx-processing

## Skill Overview
This skill acts as a comprehensive toolkit for dealing with Excel and other spreadsheet files. It provides three distinct operational modes for analyzing content, creating new spreadsheets from scratch, and editing existing spreadsheets while safely preserving formulas.

## Workflow Sequence

| Stage | Description | Workflow | Input | Output |
| :--- | :--- | :--- | :--- | :--- |
| **1. Mode Selection** | Present options to the user and capture choice. | `[assets/01-mode-selection.md](assets/01-mode-selection.md)` | Options | Selected Mode |
| **2. Context Setup** | Load configurations/assets for the chosen mode. | `[assets/02-context-setup.md](assets/02-context-setup.md)` | Selected Mode | Context |
| **3. Specialized Workflow** | Execute the logic specific to the selected mode. | `[assets/<mode-file>.md]` | Context | Results |
| **4. Outcome** | Finalize based on mode-specific criteria and verify formulas. | `[assets/04-outcome.md](assets/04-outcome.md)` | Results | Final Output |

## Pre-stage Checkpoint
- **Human in the Loop (HITL)**: By default, ask for user confirmation when choosing the mode and at the conclusion of the operation before delivering the final document.
- **Autopilot**: If the user's initial prompt explicitly requests a specific mode (e.g., "create a new spreadsheet", "read this xlsx"), the agent can autonomously select the correct mode and bypass HITL until the final step.

## Core Operation Flow

### Initialization
Before proceeding to Step 1, the agent MUST initialize the checklist in `.agents/skills-diary/xlsx-processing/[<instance-name>]/checklist.md` using the template at `[references/checklist.md](references/checklist.md)`.

### Global Stages
- **Step 1: Mode Selection**: Follow the instructions in `[assets/01-mode-selection.md](assets/01-mode-selection.md)` to capture the user's intended mode interactively or autonomously. Save this selection in the agent's internal state.
- **Step 2: Context Setup**: Follow `[assets/02-context-setup.md](assets/02-context-setup.md)` to identify files and dependencies, including the mandatory loading of `[references/formatting-standards.md](references/formatting-standards.md)` and `[references/development-guidelines.md](references/development-guidelines.md)`.

### Mode-Specific Workflow (Step 3)
Depending on the selected mode, only follow the logic in the corresponding workflow document under `assets/`:

#### Execution: Mode read-analyze
- Follow `[assets/03-01-read-analyze.md](assets/03-01-read-analyze.md)`

#### Execution: Mode create-spreadsheet
- Follow `[assets/03-02-create-spreadsheet.md](assets/03-02-create-spreadsheet.md)`

#### Execution: Mode edit-spreadsheet
- Follow `[assets/03-03-edit-spreadsheet.md](assets/03-03-edit-spreadsheet.md)`

**CRITICAL CONSTRAINT**: The agent MUST NOT utilize logic, assets, or references defined for any unselected mode. Strict segregation is required.

### Finalization
- **Step 4: Outcome**: Conclude the operation by following `[assets/04-outcome.md](assets/04-outcome.md)`. Verify outputs with `scripts/recalc.py` and hand them over to the user.

## Handover & Confirmation
The skill is successfully completed when the requested spreadsheet operation is finished and valid `.xlsx` files or extracted data are presented to the user.

A successful execution creates a directory tree representation of the output similar to:
```text
<project-dir>/
    spreadsheet.xlsx
    ...
```

## Additional Instructions

All temporary scripts generated while execution of skills (scripts which will be deleted after execution) will be written in .agents/skills-diary/temp-scripts/<timestamp>/ as directory

