# Odoo CRM & Sales UAT Library

A practical acceptance-test library for validating lead-to-order processes in Odoo CRM and Sales.

## Test Coverage

| ID | Process | Scenario | Expected Result | Priority |
|---|---|---|---|---|
| CRM-UAT-001 | Lead Creation | Create lead manually | Lead saves with mandatory fields and correct ownership | Must |
| CRM-UAT-002 | Lead Assignment | Assign lead to salesperson/team | Ownership and pipeline visibility update correctly | Must |
| CRM-UAT-003 | Duplicate Control | Create probable duplicate lead/customer | Approved duplicate-handling rule is triggered | Should |
| CRM-UAT-004 | Qualification | Complete qualification fields | Required qualification data is captured before next stage | Must |
| CRM-UAT-005 | Pipeline | Move opportunity through stages | Stage movement follows approved business rules | Must |
| CRM-UAT-006 | Lost Opportunity | Mark opportunity lost with reason | Lost reason is captured and reporting updates | Should |
| CRM-UAT-007 | Activities | Schedule call/meeting/follow-up | Activity appears for responsible user with due date | Must |
| CRM-UAT-008 | Conversion | Convert lead to opportunity/customer | Customer linkage is correct without unintended duplication | Must |
| CRM-UAT-009 | Quotation | Create quotation from opportunity | Customer, salesperson, items, prices, taxes, and terms populate correctly | Must |
| CRM-UAT-010 | Pricelist | Apply approved pricelist/discount | Correct price and discount rules are applied | Must |
| CRM-UAT-011 | Discount Control | Exceed authorized discount | System blocks or routes action according to approval design | Must |
| CRM-UAT-012 | Quotation Approval | Submit quotation requiring approval | Approval status and responsible approver are correct | Should |
| CRM-UAT-013 | Quotation Revision | Revise commercial offer | Revision remains traceable and current version is clear | Should |
| CRM-UAT-014 | Sales Order | Confirm approved quotation | Sales order is created with correct commercial terms | Must |
| CRM-UAT-015 | Invoice Trigger | Trigger invoice from sales order | Invoice follows approved invoicing policy | Must |
| CRM-UAT-016 | Cancellation | Cancel order according to policy | Status, downstream impact, and audit trail are correct | Must |
| CRM-UAT-017 | Access Control | Salesperson opens another team's restricted records | Access follows approved role/record-rule design | Must |
| CRM-UAT-018 | Sales Manager | Manager reviews team pipeline | Manager sees authorized team pipeline and KPIs | Must |
| CRM-UAT-019 | Forecast | Review expected revenue/closing date | Pipeline forecast reflects opportunity data correctly | Should |
| CRM-UAT-020 | Reporting | Generate pipeline and sales reports | Totals reconcile to source opportunities/orders | Must |
| CRM-UAT-021 | Customer History | Open customer record after multiple transactions | Related opportunities, quotations, orders, and activities are traceable | Should |
| CRM-UAT-022 | Email | Send approved quotation/email from Odoo | Message is logged against the correct business record | Should |
| CRM-UAT-023 | Sales Team | Route opportunity by team/channel | Correct sales team and salesperson rules are applied | Should |
| CRM-UAT-024 | Mandatory Data | Attempt confirmation with missing critical information | System prevents progression where approved mandatory controls exist | Must |

## Real-Estate Extension Scenarios

| ID | Scenario | Expected Result |
|---|---|---|
| RE-UAT-001 | Select available unit for opportunity | Only eligible inventory is selectable |
| RE-UAT-002 | Reserve a unit | Unit status changes according to approved reservation workflow |
| RE-UAT-003 | Attempt overlapping active reservation | System prevents conflicting reservation according to business rule |
| RE-UAT-004 | Apply payment plan | Installment schedule equals approved contract value |
| RE-UAT-005 | Convert reservation to contract | Customer, unit, price, discounts, and payment terms transfer correctly |
| RE-UAT-006 | Cancel reservation | Unit is released according to approval/refund policy |
| RE-UAT-007 | Broker sale | Broker/channel attribution is retained for commission processing |
| RE-UAT-008 | Sales commission eligibility | Commission basis uses approved sale/payment milestone rules |

## Lead-to-Sale End-to-End Scenario

```text
Lead
  ↓
Qualification
  ↓
Opportunity
  ↓
Activities / Follow-up
  ↓
Quotation
  ↓
Approval
  ↓
Sales Order / Reservation
  ↓
Contract / Invoice
  ↓
Collection
  ↓
Commission / Reporting
```

## Sign-Off Minimum Criteria

- [ ] Must scenarios passed
- [ ] Critical defects = 0
- [ ] Sales stages approved
- [ ] Mandatory fields approved
- [ ] Discount/approval controls tested
- [ ] Access rights tested
- [ ] Reports reconcile to source data
- [ ] Real-estate reservation rules tested where applicable
