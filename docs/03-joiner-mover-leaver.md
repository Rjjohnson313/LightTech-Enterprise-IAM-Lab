# 03 — Joiner, Mover, Leaver (JML)

## Joiner — Honey H. Wells

**Goal:** Make a new Finance employee available in Okta and show the correct application assignment.

1. Created Honey H. Wells (`hwells`) in Active Directory.
2. Added the identity to `LT-Finance-Users`.
3. Imported and validated the account in Okta.
4. Verified imported Finance group membership and Finance Portal assignment.

**Evidence:** [AD account](../screenshots/02-joiner/honey-ad-user.png), [AD membership](../screenshots/02-joiner/honey-ad-group-membership.png), [Okta group](../screenshots/02-joiner/honey-okta-finance-group.png), [portal](../screenshots/02-joiner/honey-okta-finance-assignment.png).

## Mover — Finance to HR

**Goal:** Change access when a user changes departments.

1. Removed Honey from `LT-Finance-Users` and added the HR group in AD.
2. Refreshed imports into Okta.
3. Confirmed Finance assignment was removed and HR group membership reflected the transfer.
4. Checked user dashboard visibility for the HR portal and absence of Finance access.

**Evidence:** [Group change](../screenshots/03-mover/honey-hr-group-change.png), [Finance access removed](../screenshots/03-mover/honey-finance-access-removed.png), [HR dashboard](../screenshots/03-mover/honey-hr-dashboard.png).

## Leaver — Disable and deprovision

**Goal:** Block future sign-in and verify downstream application assignment cleanup.

1. Disabled Honey's AD account.
2. Performed an import and verified Honey's Okta account displayed **Deactivated**.
3. Tested and observed a denied login for the deactivated identity.
4. Examined Okta System Log entries for Finance and HR application membership removal, account deactivation, session clearing, and an import-triggered deletion-related event.
5. Re-checked the Okta profile: the account remained **Deactivated**, not permanently deleted.

**Evidence:** [AD disabled](../screenshots/04-leaver/honey-ad-account-disabled.png), [Okta status](../screenshots/04-leaver/honey-okta-deactivated.png), [denied login](../screenshots/04-leaver/honey-login-denied.png).

**Interpretation:** Application memberships were removed and Okta logged a successful session-clearing operation; this does not prove all external service sessions were terminated. The successful import-related deletion event did not establish permanent account deletion.

Read the [offboarding audit report](../audit-reports/offboarding-audit.md).
