# 04 — RBAC and Application Assignments

## Group-based access matrix

| Group | Okta demo app | Expected user |
|---|---|---|
| `LT-Finance-Users` | Finance Portal | `finance.user` |
| `LT-HR-Users` | HR Portal | `hr.user` |

Both portals are **bookmark applications**. Each bookmark's assignment can determine whether its tile is visible in the Okta dashboard. This does **not** test access control at `example.com`, nor should it be described as enforcing backend authorization.

## Validation

- Confirmed the Finance group assigned to Finance Portal.
- Confirmed the HR group assigned to HR Portal.
- Confirmed appropriate user assignment and absence of unrelated portal tiles.
- Used group membership as the baseline for a manual least-privilege review.

See [access review and remediation](../audit-reports/access-review.md).
