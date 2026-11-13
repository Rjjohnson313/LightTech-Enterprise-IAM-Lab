# 06 — Identity Governance and Access Review

## Access certification exercise

Manually reviewed Okta group memberships, application assignments, and one deactivated identity. Review decisions were based on the lab's expected department roles; **no independent business approver was involved**.

| User | Expected entitlement | Review decision |
|---|---|---|
| `finance.user` | Finance Portal via `LT-Finance-Users` | Retain |
| `hr.user` | HR Portal via `LT-HR-Users` | Retain |
| Honey H. Wells | Deactivated identity, no active Finance/HR assignment | Remain deactivated |

## Simulated exception: LT-IAM-001

1. Intentionally granted `hr.user` a **direct** Finance Portal assignment while leaving `LT-Finance-Users` unchanged.
2. Verified `hr.user` appeared under Finance Portal assignments but was not in the Finance group.
3. Removed the direct assignment and confirmed `finance.user` retained Finance access.
4. Confirmed HR access for `hr.user` and group assignment `LT-HR-Users` remained intact.

**Finding:** A direct app assignment created a least-privilege exception against the lab's group-based policy. **Status:** Resolved.

**Evidence:** [Before](../screenshots/07-governance/finance-access-before-remediation.png) · [After](../screenshots/07-governance/finance-access-after-remediation.png)

This is a **controlled simulation**, not a real security incident. See [access review report](../audit-reports/access-review.md).
