# Process Checklist

## Phase 1: Context Setup
- [ ] Choose appropriate processing mode (read-analyze, create-spreadsheet, edit-spreadsheet)
- [ ] Identify target file(s) and paths
- [ ] Load `[formatting-standards.md](references/formatting-standards.md)` and `[development-guidelines.md](references/development-guidelines.md)`

## Phase 2: Specialized Workflow Execution
- [ ] (read-analyze) Execute data extraction or analysis
- [ ] (create-spreadsheet) Generate new workbook using openpyxl/pandas
- [ ] (edit-spreadsheet) Modify existing workbook safely preserving formulas
- [ ] Apply formatting rules and naming conventions

## Phase 3: Finalization
- [ ] Ensure ZERO formula errors
- [ ] Save updated workbook
- [ ] Run `scripts/recalc.py` to evaluate formulas (if any formulas exist)
- [ ] Handover file to user
