# Odoo HR & Payroll UAT Library

A practical UAT library for validating employee master data, attendance, leave, payroll processing, access, and reporting.

> Payroll, tax, social-insurance, labor-law, and statutory rules must be validated against the applicable country localization and approved legal/finance requirements.

## Test Coverage

| ID | Process | Scenario | Expected Result | Priority |
|---|---|---|---|---|
| HR-UAT-001 | Employee Master | Create new employee | Employee record saves with mandatory approved fields | Must |
| HR-UAT-002 | Employee Master | Update department/job/manager | Organizational data updates correctly and remains traceable | Must |
| HR-UAT-003 | Contract | Create employee contract | Contract dates, wage components, structure, and status are correct | Must |
| HR-UAT-004 | Access | HR user views authorized employee data | Access follows approved HR role design | Must |
| HR-UAT-005 | Access | Unauthorized user attempts sensitive HR access | Restricted employee/payroll data is blocked | Must |
| HR-UAT-006 | Attendance | Import/register attendance | Attendance is linked to correct employee and work date | Must |
| HR-UAT-007 | Attendance | Missing checkout / exception | Exception is detected and handled according to approved process | Should |
| HR-UAT-008 | Attendance | Late arrival / early departure | Result follows configured schedule and approved policy | Should |
| HR-UAT-009 | Leave | Submit leave request | Request routes to correct approver and balance is validated | Must |
| HR-UAT-010 | Leave | Approve leave | Leave balance and calendar update correctly | Must |
| HR-UAT-011 | Leave | Reject/cancel leave | Status and balance behave according to approved workflow | Should |
| HR-UAT-012 | Public Holiday | Attendance/payroll across holiday | Calendar and payroll treatment follow approved configuration | Should |
| HR-UAT-013 | Payroll | Generate payroll batch | Eligible employees are included with correct structure | Must |
| HR-UAT-014 | Payroll | Calculate standard payslip | Earnings, deductions, net pay, and employer costs follow approved rules | Must |
| HR-UAT-015 | Payroll | Attendance-based deduction | Deduction follows approved attendance/payroll rule | Must |
| HR-UAT-016 | Payroll | Leave impact on payroll | Paid/unpaid leave is reflected correctly | Must |
| HR-UAT-017 | Payroll | Allowance / recurring input | Approved allowance appears correctly | Must |
| HR-UAT-018 | Payroll | One-time deduction/input | Approved one-time value appears only in intended period | Must |
| HR-UAT-019 | Payroll | Payroll validation / approval | Unauthorized validation is blocked and approved workflow is enforced | Must |
| HR-UAT-020 | Payroll | Finalize payroll | Finalized payroll becomes controlled according to approved process | Must |
| HR-UAT-021 | Payroll | Accounting posting | Payroll accounting entry reconciles to payroll totals | Must |
| HR-UAT-022 | Payroll | Bank transfer output | Net-pay output reconciles to approved payroll register | Should |
| HR-UAT-023 | Reporting | Payroll register | Report totals reconcile to payslips and accounting | Must |
| HR-UAT-024 | Offboarding | Terminate employee | Contract/status/access/process dates update according to approved workflow | Must |

## End-to-End HR Scenario

```text
Employee Master
→ Contract
→ Work Schedule
→ Attendance / Leave
→ Payroll Inputs
→ Payroll Calculation
→ Review / Approval
→ Accounting
→ Payment Output
→ Reporting
```

## Sign-Off Minimum Criteria

- [ ] Employee master fields approved
- [ ] HR access controls tested
- [ ] Attendance exceptions tested
- [ ] Leave balances validated
- [ ] Payroll formulas independently reconciled
- [ ] Payroll accounting reconciled
- [ ] Net-pay output reconciled
- [ ] Local statutory rules signed off by responsible subject-matter owners
- [ ] Critical defects = 0
