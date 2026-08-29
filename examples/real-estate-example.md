# Example — Real Estate Developer

This example shows how the playbook can be adapted for a real-estate developer.

## Candidate Modules
- CRM
- Sales
- Accounting
- Approvals
- Documents
- Employees
- Attendance
- Helpdesk
- Maintenance
- Custom unit inventory
- Custom reservation / contract workflow
- Brokerage commission workflow

## Example Dimensions
- Project
- Phase
- Building
- Unit
- Department
- Branch
- Sales channel
- Broker
- Customer segment
- Bank
- Payment method

## Example End-to-End UAT Scenario

```text
Lead
→ Opportunity
→ Unit Selection
→ Reservation
→ Customer Creation
→ Contract
→ Installment Schedule
→ Collection
→ Cheque Tracking
→ Commission Calculation
→ Accounting Entries
→ Management Reporting
```

## Example Controls
- Unit cannot have overlapping active reservations.
- Contract approval required before final confirmation.
- Payment schedule must reconcile to contract value.
- Customer receipts must post to approved journals.
- Broker commission requires approved eligibility and calculation basis.
- Financial reports must reconcile to the general ledger.
