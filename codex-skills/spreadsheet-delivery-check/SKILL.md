---
name: spreadsheet-delivery-check
description: Mandatory final quality gate for spreadsheet work. Use whenever Codex creates, imports, repairs, updates, reformats, or writes values or formulas in any Feishu/Lark Sheet, Excel workbook, Google Sheet, CSV-backed model, profit calculator, financial model, or operational data table. After the final write and before delivery, run formula-error scanning, hidden invalid-reference scanning, and key-result readback; do not claim completion until all applicable checks pass.
---

# Spreadsheet Delivery Check

Treat this skill as the final gate after every spreadsheet creation or modification. Run it after the last write, not before it. If any later write changes the workbook, repeat the affected checks.

## Required three-part verification

### 1. Scan formula errors

- Scan every relevant worksheet and the complete used region, not only the cells just edited.
- Detect formula compilation failures and runtime errors, including `#REF!`, `#DIV/0!`, `#VALUE!`, `#NAME?`, `#NULL!`, `#NUM!`, and `#N/A`.
- For Feishu/Lark Sheets, run `lark-cli sheets +formula-verify` after formulas are written. Completion requires:
  - `status = success`
  - `has_more = false`
  - `total_errors = 0`
  - `compile_errors = []`
- If scanning is partial, split by worksheet or range until all used cells are covered.
- Fix every error and rerun the scan. Do not hide a broken formula by wrapping it in `IFERROR`.
- If the workbook contains no formulas, record that fact and continue with checks 2 and 3.

### 2. Scan hidden invalid references

- Inspect raw formula text independently of displayed values.
- Search all formula-bearing cells for invalid-reference tokens such as `#REF!` and references to deleted worksheets, deleted ranges, broken named ranges, or invalid external sources.
- Pay special attention to formulas wrapped in `IFERROR`, `IFNA`, or conditional logic because displayed zeros or blanks can conceal broken dependencies.
- Confirm that the invalid-reference count is zero. A clean runtime-error scan alone is insufficient.
- If a reference is intentionally unavailable, replace it with an explicit documented input or assumption; never leave a broken token in the formula.

### 3. Read back key results

- Read the values back from the actual saved or online workbook after the final write.
- Verify all independently testable requirements from the user's request.
- At minimum, check:
  - critical inputs and their units;
  - primary outputs, totals, margins, rates, or decision cells;
  - cross-sheet links and dependent outputs;
  - first, middle, and last representative records for repeated formulas;
  - boundary cases such as zero, negative values, empty inputs, and denominator safety when applicable;
  - number types and formats for currency, percentages, dates, and counts.
- For financial or calculation models, independently reproduce 3–5 representative results outside the workbook and compare them with the readback values.
- For online spreadsheets, a successful write response is not proof. Use the platform's read command to confirm the persisted values.

## Failure handling

Do not state that the spreadsheet is complete while any check is failing or incomplete. Continue repairing and rerunning the checks. If repair is genuinely blocked, report:

- the exact worksheet and cell addresses;
- the formula or value involved;
- the remaining error type;
- the missing input, permission, or external dependency needed.

## Delivery record

Include a concise verification record in the final response:

- formula scan: formula count, error count, and full-scan status;
- hidden-reference scan: invalid formula-reference count;
- key-result readback: the important values checked;
- final workbook URL or absolute path and, when available, revision/version.

Never claim that checks were run unless the tools were actually executed and their results were read.
