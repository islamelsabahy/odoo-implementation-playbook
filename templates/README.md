# Excel-Ready Templates

These CSV files are designed to open directly in Microsoft Excel, Google Sheets, or LibreOffice Calc.

## Included Templates

| File | Purpose |
|---|---|
| `requirements-register.csv` | Track business, functional, reporting, security, integration, and data requirements |
| `uat-test-cases.csv` | Execute and sign off user acceptance tests |
| `gap-analysis.csv` | Classify requirements against Odoo standard capability and approved resolution approach |
| `defect-log.csv` | Track UAT defects, severity, ownership, status, retesting, and root cause |
| `raid-log.csv` | Track risks, assumptions, issues, and dependencies |

## Recommended Workbook Structure

For a live Odoo project, these CSVs can be combined into one workbook with tabs such as:

```text
01 Requirements
02 Gap Analysis
03 UAT Test Cases
04 Defects
05 RAID
06 Decisions
07 Change Requests
08 Migration
09 Go-Live Readiness
10 Hypercare
```

## Usage Rules

1. Keep a stable ID for every record.
2. Never delete closed requirements or defects; close them with status instead.
3. Link defects to test case IDs.
4. Link gaps to requirement IDs.
5. Keep one accountable owner for each open item.
6. Record approvals and decisions explicitly.
7. Do not place confidential production data in a public repository.
8. Replace all example rows with approved dummy or project-controlled data before external sharing.
