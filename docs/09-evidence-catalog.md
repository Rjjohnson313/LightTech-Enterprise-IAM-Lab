# 09 — Screenshot Evidence Catalog

This directory includes a **curated, public-safe subset** of the original lab screenshots. Some images were **cropped to remove browser URLs, tenant references, live login context, or SAML identifiers**. The source archive remains outside this repository.

## Directory and provisioning

- [`screenshots/01-directory/`](../screenshots/01-directory/) — AD structure, agent health, imported groups, application group assignment.
- [`screenshots/02-joiner/`](../screenshots/02-joiner/) — Honey H. Wells AD creation, Finance group membership, Okta user/app assignment.
- [`screenshots/03-mover/`](../screenshots/03-mover/) — HR group change, Finance removal, HR dashboard result.
- [`screenshots/04-leaver/`](../screenshots/04-leaver/) — AD disablement, Okta deactivation, denied login and event evidence.

## Federation, authentication and governance

- [`screenshots/05-saml/`](../screenshots/05-saml/) — SAML configuration and **cropped** successful SP-initiated login result.
- [`screenshots/06-authentication/`](../screenshots/06-authentication/) — MFA policy/challenge, Okta Verify success, System Log result.
- [`screenshots/07-governance/`](../screenshots/07-governance/) — Before and after the deliberate direct-assignment exception.

### Omitted from the public repository

The original archive includes additional screenshots of **raw SAML transactions**, **assertion details**, **IdP metadata / signing material**, and related configuration. Those are **not** included in this public-ready copy. Do not post authentication responses, raw assertion blobs, Okta tokens, authenticator activation secrets, full identity provider URLs, or credentials.

### Redaction notes

- `06-authentication/frostid-mfa-challenge.png` was cropped to remove the browser address bar (tenant hostname and app path).
- `04-leaver/honey-login-denied.png` has the masked password field blanked.
- `04-leaver/honey-deactivation-system-log.png` and `06-authentication/frostid-mfa-system-log.png` are small, partly blurred excerpts showing only event type and outcome. The first shows a **failed login attempt** by the deactivated user, not the deactivation event itself; the deactivation events are described in the [offboarding audit](../audit-reports/offboarding-audit.md) without a screenshot.

### Evidence qualification

- `Finance Portal` / `HR Portal` pictures show Okta **bookmark** visibility and assignment.
- Screenshots and written notes corroborate **lab results**, not production compliance.
- Audit reports are human-written test records; no third-party auditor or app owner approved them.
