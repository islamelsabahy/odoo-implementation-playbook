# Odoo Finance UAT Library

A practical acceptance-test library for validating core finance processes before go-live.

> Adapt account names, taxes, journals, localization, currencies, approval rules, and statutory requirements to the target company and country.

## Test Coverage

| ID | Process | Scenario | Expected Result | Priority |
|---|---|---|---|---|
| FIN-UAT-001 | Customer Invoice | Create and post a standard customer invoice | Correct receivable, revenue, tax, journal, date, and partner entries are posted | Must |
| FIN-UAT-002 | Customer Payment | Register full payment against posted invoice | Invoice becomes paid and bank/cash journal is updated correctly | Must |
| FIN-UAT-003 | Partial Collection | Register partial payment | Residual amount remains correct and reconciliation is traceable | Must |
| FIN-UAT-004 | Credit Note | Reverse a posted invoice using a credit note | Credit note references source transaction and balances reconcile | Must |
| FIN-UAT-005 | Vendor Bill | Create and post vendor bill | Payable, expense/asset, tax, and journal entries are correct | Must |
| FIN-UAT-006 | Vendor Payment | Pay posted vendor bill | Payable is reconciled and payment journal reflects the transaction | Must |
| FIN-UAT-007 | Multi-Currency | Post foreign-currency invoice and payment | Foreign currency, company currency, and exchange differences are correct | Should |
| FIN-UAT-008 | Bank Reconciliation | Match imported/manual bank transaction to invoice/payment | Statement line reconciles to correct accounting entry without duplicate posting | Must |
| FIN-UAT-009 | Cash Receipt | Receive customer payment into cash journal | Cash balance and customer receivable reconcile correctly | Must |
| FIN-UAT-010 | Manual Journal Entry | Post approved GL adjustment | Debit equals credit and access/approval restrictions are enforced | Must |
| FIN-UAT-011 | Tax | Post transaction with configured sales tax | Tax base and tax amount are posted to correct accounts | Must |
| FIN-UAT-012 | Withholding | Apply withholding where applicable | Withholding amount and payable/receivable treatment follow approved design | Should |
| FIN-UAT-013 | Customer Aging | Generate receivable aging report | Aging buckets reconcile to open receivable balances | Must |
| FIN-UAT-014 | Vendor Aging | Generate payable aging report | Aging buckets reconcile to open payable balances | Must |
| FIN-UAT-015 | Trial Balance | Generate trial balance for test period | Total debits equal credits and balances reconcile to ledger | Must |
| FIN-UAT-016 | Profit & Loss | Generate P&L | Revenue and expense balances match posted transactions and approved account mapping | Must |
| FIN-UAT-017 | Balance Sheet | Generate balance sheet | Assets, liabilities, and equity reconcile to the general ledger | Must |
| FIN-UAT-018 | Lock Date | Attempt posting into locked period | System blocks unauthorized posting and enforces approved lock-date policy | Must |
| FIN-UAT-019 | Access Control | Non-authorized user attempts to post journal entry | Action is blocked according to role design | Must |
| FIN-UAT-020 | Audit Trail | Review edited/cancelled finance document history | User, date, action, and traceability are available according to approved control design | Must |
| FIN-UAT-021 | Opening Balances | Validate migrated opening balances | Control totals reconcile to approved legacy closing balances | Must |
| FIN-UAT-022 | Customer Statement | Generate customer statement | Statement includes correct opening, transactions, payments, and balance | Should |
| FIN-UAT-023 | Payment Terms | Invoice using installment/payment terms | Due dates and amounts follow configured terms | Must |
| FIN-UAT-024 | Analytic Dimensions | Post transaction with project/department dimension | Analytic allocation appears correctly in operational and management reporting | Should |

## End-to-End Finance Scenario

```text
Customer / Vendor Master
        ↓
Invoice / Bill
        ↓
Tax & Dimensions
        ↓
Approval (if applicable)
        ↓
Posting
        ↓
Collection / Payment
        ↓
Bank Reconciliation
        ↓
GL Reconciliation
        ↓
Aging / Trial Balance / P&L / Balance Sheet
```

## Finance Sign-Off Minimum Criteria

- [ ] All Must scenarios executed
- [ ] Critical defects = 0
- [ ] Opening balances reconciled
- [ ] Customer and vendor balances reconciled
- [ ] Trial balance accepted
- [ ] Financial statements reviewed
- [ ] Bank/cash journals validated
- [ ] Access rights approved
- [ ] Tax/localization behavior approved by responsible finance owner
- [ ] Month-end controls tested

## Evidence

For each executed test, retain:
- Tester
- Date
- Test data reference
- Screenshot or report evidence
- Actual result
- Pass / Fail
- Defect reference if failed
- Business owner sign-off
