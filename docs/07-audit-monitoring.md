# 07 — Okta Audit and Monitoring

## Procedure

Using **Reports → System Log**, investigated events associated with Honey H. Wells and `hr.user`. Evaluated actor, target, event type, timestamp where available, and outcome. Recorded outcomes in the lab audit reports without inventing missing timestamp or IP data.

## Offboarding events

| Event / operation | Observed outcome | Interpretation |
|---|---|---|
| Account deactivation | Successful | Okta recorded a successful deactivation operation |
| Finance Portal membership removal | Successful | Finance app membership removal processed |
| HR Portal membership removal | Successful | HR app membership removal processed |
| Session clearing | Successful | Okta processed a session-clearing operation |
| Import-triggered user deletion-related event | Successful | Event occurred, **but profile still displayed Deactivated** |

**Note:** Timestamps were not recorded, and Honey's Finance membership had already been removed at the mover stage, so the Finance removal event cannot be placed in the leaver stage from these records alone.

## SSO / MFA events

- `hr.user` was associated with successful FrostID SAML login activity.
- Okta Verify MFA event showed **Success**.
- Authentication method evidence and application sign-in evidence may be separate System Log events.

## Interpretive caution

Event names and outcomes must be interpreted in the context of the resulting account state. “Delete user triggered by import process — Successful” did **not** mean the Okta user profile disappeared. An Okta session-clearing event does not certify revocation of all external app sessions.

[Offboarding audit](../audit-reports/offboarding-audit.md) · [Authentication audit](../audit-reports/authentication-mfa-audit.md)
