# 08 — Troubleshooting Log and Lessons

## AD / workstation integration

**Issue:** Windows 11 workstation experienced domain communication/trust and DNS setup issues during initial lab build.

**Approach:** Validated DNS services and LDAP SRV resolution on `LT-DC01`, corrected network configuration, repaired the workstation trust relationship, and confirmed domain login.

## Okta sign-in policy / lab VM factors

**Issue:** A phishing-resistant WebAuthn / FIDO2 requirement prevented progress in a virtual environment without a compatible biometric or hardware security key.

**Approach:** Recovered the intended test login flow, then created a **dedicated FrostID application authentication policy** with a suitable two-factor requirement. Avoided modifying the administrator app policy as part of subsequent tests.

## FrostID SAML `InResponseTo`

**Issue:** Opening the FrostID SAML demo from Okta's application tile resulted in an `InResponseTo` error after authentication.

**Finding:** FrostID's **SP-initiated Run Test Login** path worked and reached Login Complete. The original IdP-initiated route was not demonstrated as working.

**Lesson:** For SAML debugging, distinguish IdP-initiated and SP-initiated flows, use a clear test request context, and inspect `InResponseTo` and NameID warning information before changing settings.

## Import-triggered deletion event

**Issue:** System Log indicated an import-triggered deletion-related event marked successful.

**Finding:** An independent profile check showed the identity still **Deactivated**.

**Lesson:** Validate the final object state rather than interpreting an event label as permanent deletion.
