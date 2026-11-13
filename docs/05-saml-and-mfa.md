# 05 — SAML 2.0 and MFA

## Identity federation

- **IdP:** Okta.
- **SP:** FrostID SAML Demo sandbox.
- **Entity ID / Audience:** `https://sandbox-sp.frostid.se`.
- **ACS:** `https://sandbox-sp.frostid.se/acs`.
- **Test flow:** SP-initiated, started by FrostID **Run Test Login**.

Imported Okta IdP metadata was accepted as valid by FrostID. FrostID then returned a **Login Complete** screen for the successful SP-initiated login.

## MFA enforcement

| Setting | Lab value |
|---|---|
| Application auth policy | `LAB-FrostID-MFA-Policy` |
| Rule | `LAB-FrostID-Require-MFA` |
| Group scope | `LT-HR-Users` |
| Authentication requirement | Any two factor types |
| Prompt frequency | Every sign-in to the resource |
| Authenticator verified | Okta Verify |
| Observed MFA event outcome | Success |

A dedicated **application authentication policy** was used, avoiding changes to the Okta Admin Console's own sign-in policy.

## Interoperability observation

An Okta dashboard-initiated FrostID launch produced an `InResponseTo` error after authentication. The separate **SP-initiated flow succeeded**, indicating the setup worked for the tested request/response flow. Do not infer successful IdP-initiated SSO from the SP-initiated test.

**Likely explanation (not independently confirmed):** a launch from the Okta tile is IdP-initiated, so no SP `AuthnRequest` exists and the SAML response carries no `InResponseTo` value for the SP to match. An SP that validates `InResponseTo` against a request it issued will reject such an unsolicited response. In the SP-initiated test the SP issued the request, so the check passed (FrostID's result page confirmed signature, audience, `InResponseTo` and validity window).

## Known configuration gaps (acceptable for a sandbox)

The SAML settings screenshots show choices that would be reviewed before production use: assertions are **unencrypted** (responses and assertions are signed), SAML Single Logout is **disabled**, SAML signed requests are **disabled**, and NameID format is **Unspecified**. None were changed for this lab.

## Evidence

- [SAML settings](../screenshots/05-saml/frostid-saml-settings.png)
- [Login complete — cropped, identifiers excluded](../screenshots/05-saml/frostid-login-complete-safe-excerpt.png)
- [MFA policy](../screenshots/06-authentication/frostid-mfa-policy.png)
- [MFA success](../screenshots/06-authentication/frostid-mfa-success.png)
- [MFA System Log](../screenshots/06-authentication/frostid-mfa-system-log.png)

More details: [authentication audit](../audit-reports/authentication-mfa-audit.md).
