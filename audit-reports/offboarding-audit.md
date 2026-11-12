# Offboarding Audit — Honey H. Wells

**Identity:** Honey H. Wells (`hwells`) · **Environment:** AD + Okta · **Review:** Manual lab leaver audit · **Status:** Completed

## Observed evidence

| Control | Okta / AD observation | Outcome |
|---|---|---|
| AD account status | AD account disabled | Verified |
| Okta lifecycle action | User deactivation event | Successful |
| Finance app deprovisioning | Remove user application membership | Successful |
| HR app deprovisioning | Remove user application membership | Successful |
| Session handling | Clear user session | Successful |
| Import-triggered lifecycle action | “Delete user triggered by import process” | Successful event, **not verified permanent deletion** |
| Current Okta status | Profile retained as Deactivated | Verified |

**Actor observation:** The Okta deactivation event listed the lab administrator account as actor. The overall sequence involved AD changes and directory import, but the event actor alone does not prove every upstream action's origin.

**Timing caveat:** Honey's Finance assignment was already removed during the earlier mover step (Finance to HR). System Log timestamps were not captured for this report, so it does not establish whether the listed Finance membership-removal event belongs to the mover or the leaver stage. The HR removal, deactivation and session-clearing events are the leaver-stage evidence.

## Interpretation

The logged events and profile checks support deprovisioning of the two demonstrated application memberships and Okta account deactivation. The session-clearing event was successful. The import-triggered deletion-related event did not cause a confirmed permanent removal of the Okta account; the profile remained **Deactivated**.

**Assessment:** PASS for the specifically observed lab controls. Not evidence of global session revocation, production compliance, or deletion from every application.
