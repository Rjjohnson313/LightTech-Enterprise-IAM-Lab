# SAML 2.0 SSO and MFA Flow

```mermaid
sequenceDiagram
    autonumber
    participant U as HR test user
    participant SP as FrostID sandbox SP
    participant O as Okta IdP
    participant MFA as Okta Verify
    U->>SP: Run Test Login (SP-initiated)
    SP->>O: SAML AuthnRequest
    O->>U: User authentication / policy evaluation
    O->>MFA: Request second-factor verification
    MFA-->>O: Successful Okta Verify result
    O-->>SP: Signed SAMLResponse
    SP->>SP: Validate signature, audience and InResponseTo
    SP-->>U: Login complete
```

**Configuration observed:** FrostID service provider ACS `https://sandbox-sp.frostid.se/acs`, audience `https://sandbox-sp.frostid.se`; policy `LAB-FrostID-MFA-Policy`; rule `LAB-FrostID-Require-MFA`; scoped to `LT-HR-Users`.

**Result:** The FrostID-initiated login completed, and Okta System Log showed successful Okta Verify MFA. Launching from the Okta end-user application tile produced an `InResponseTo` error at the SP. The successful test does **not** establish IdP-initiated compatibility.

**Evidence:** [SAML and MFA walkthrough](../docs/05-saml-and-mfa.md) · [MFA audit](../audit-reports/authentication-mfa-audit.md)
