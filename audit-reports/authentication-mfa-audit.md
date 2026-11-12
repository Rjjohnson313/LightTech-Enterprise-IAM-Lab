# Authentication and MFA Audit

**Application:** FrostID SAML Demo · **Identity:** `hr.user` · **IdP:** Okta · **Protocol:** SAML 2.0 · **Review:** Completed

## Auth policy and test

| Control | Configuration / result |
|---|---|
| Application policy | `LAB-FrostID-MFA-Policy` |
| Rule | `LAB-FrostID-Require-MFA` |
| Scope | `LT-HR-Users` |
| Requirement | Any two factor types |
| Re-authentication | Every sign-in to resource |
| MFA authenticator | Okta Verify |
| MFA outcome | Successful |
| SAML SP-initiated login | Successful |
| System Log | Successful authentication / MFA activity located |

**Compatibility observation:** Okta dashboard-initiated launch caused an `InResponseTo` error at the FrostID SP. The **FrostID-initiated** test succeeded and displayed Login Complete. Therefore, the verified success is limited to the SP-initiated route.

**Assessment:** PASS for tested Okta Verify MFA and successful SP-initiated SAML login. No claim is made that IdP-initiated login was functioning.
