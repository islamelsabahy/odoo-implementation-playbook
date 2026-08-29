# Data Migration Tracker

| Dataset | Source | Owner | Volume | Cleaned | Mapping Complete | Test Import | Validated | Final Import | Notes |
|---|---|---|---:|---|---|---|---|---|---|
| Customers | Legacy ERP | Finance | 5000 | No | No | No | No | No | |

## Migration Cycle

```text
Extract
→ Profile
→ Clean
→ Deduplicate
→ Map
→ Transform
→ Test Import
→ Reconcile
→ Business Sign-off
→ Final Extract
→ Production Import
→ Final Reconciliation
```

## Reconciliation

Every migrated dataset should define measurable reconciliation criteria such as:
- Record count
- Control totals
- Opening balance totals
- Outstanding receivables
- Outstanding payables
- Inventory quantities
- Contract values
