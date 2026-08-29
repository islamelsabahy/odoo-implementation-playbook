# Odoo Purchase & Inventory UAT Library

A practical UAT library for validating procure-to-pay and inventory-control processes in Odoo.

## Purchase Test Coverage

| ID | Process | Scenario | Expected Result | Priority |
|---|---|---|---|---|
| PUR-UAT-001 | Vendor Master | Create vendor | Vendor saves with approved mandatory commercial/accounting fields | Must |
| PUR-UAT-002 | RFQ | Create request for quotation | Vendor, items, quantities, prices, taxes, and dates are correct | Must |
| PUR-UAT-003 | Approval | RFQ/order exceeds approval threshold | Correct approval workflow is triggered | Must |
| PUR-UAT-004 | Purchase Order | Confirm approved RFQ | Purchase order is created with correct terms and status | Must |
| PUR-UAT-005 | Receipt | Receive full ordered quantity | Stock receipt updates correct product/location quantities | Must |
| PUR-UAT-006 | Partial Receipt | Receive part of ordered quantity | Received and outstanding quantities remain correct | Must |
| PUR-UAT-007 | Backorder | Confirm partial receipt with balance outstanding | Backorder behavior follows approved process | Should |
| PUR-UAT-008 | Vendor Bill | Create vendor bill from purchase flow | Bill quantities/prices match approved invoicing policy | Must |
| PUR-UAT-009 | Three-Way Control | Compare PO, receipt, and vendor bill | Exceptions are identifiable and handled according to control design | Must |
| PUR-UAT-010 | Return to Vendor | Return received goods | Inventory and related valuation/document trail update correctly | Should |
| PUR-UAT-011 | Cancellation | Cancel eligible PO | Cancellation rules and downstream document impacts are correct | Should |
| PUR-UAT-012 | Access | Unauthorized user attempts purchase confirmation | System blocks action according to role/approval design | Must |

## Inventory Test Coverage

| ID | Process | Scenario | Expected Result | Priority |
|---|---|---|---|---|
| INV-UAT-001 | Product Master | Create stockable product | Product configuration, UoM, category, costing, and routes are correct | Must |
| INV-UAT-002 | Receipt | Receive stock into warehouse | On-hand quantity updates in correct location | Must |
| INV-UAT-003 | Internal Transfer | Move stock between locations | Source and destination quantities update correctly | Must |
| INV-UAT-004 | Delivery | Deliver product from stock | Stock decreases from correct location and document traceability is retained | Must |
| INV-UAT-005 | Lot/Serial | Receive and issue tracked product | Lot/serial traceability works end-to-end | Should |
| INV-UAT-006 | Inventory Count | Perform physical inventory adjustment | Approved difference posts correctly and remains auditable | Must |
| INV-UAT-007 | Negative Stock | Attempt transaction violating approved stock policy | System behavior follows configured business rule | Must |
| INV-UAT-008 | Reordering | Reach replenishment threshold | Replenishment recommendation/order follows approved rule | Should |
| INV-UAT-009 | Valuation | Post receipt/delivery for valued inventory | Inventory valuation and accounting entries follow approved costing design | Must |
| INV-UAT-010 | Returns | Customer/internal return | Quantity and valuation reverse/update correctly | Should |
| INV-UAT-011 | Warehouse Access | Restricted user accesses unauthorized location/operation | Access follows approved warehouse security model | Must |
| INV-UAT-012 | Reporting | Compare stock report to transaction history | On-hand and movement history reconcile | Must |

## End-to-End Procure-to-Pay Scenario

```text
Purchase Request / Need
→ RFQ
→ Approval
→ Purchase Order
→ Receipt
→ Quality / Quantity Validation
→ Vendor Bill
→ Reconciliation
→ Vendor Payment
→ Reporting
```

## Sign-Off Minimum Criteria

- [ ] Purchase approval matrix tested
- [ ] Partial receipts tested
- [ ] Returns tested
- [ ] Vendor bill matching tested
- [ ] Physical count process tested
- [ ] Inventory valuation reconciled where applicable
- [ ] Warehouse permissions tested
- [ ] Critical defects = 0
