# Cutover Plan

| Seq | Activity | Owner | Planned Start | Planned End | Dependency | Validation | Status |
|---:|---|---|---|---|---|---|---|
| 1 | Freeze legacy transactions | Business | | | | Confirmed | Planned |
| 2 | Final data extract | Data Team | | | 1 | File checksum | Planned |
| 3 | Production migration | Partner | | | 2 | Import log | Planned |
| 4 | Reconciliation | Finance | | | 3 | Signed reconciliation | Planned |
| 5 | Enable users | IT | | | 4 | Login validation | Planned |
| 6 | Go-live | Sponsor | | | 5 | Go decision | Planned |

## Rollback Criteria
Define objective conditions that trigger rollback or delay.
