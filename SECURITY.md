# Public Evidence and Security Handling

This portfolio includes **synthetic accounts** and a **curated** selection of lab screenshots. It deliberately omits raw SAML responses/assertions, unredacted identity provider metadata, and embedded Okta app URLs.

Before publishing **any additional material**, check for:

- Passwords, MFA/OTP codes, enrollment QR codes, activation secrets, recovery keys.
- SAMLResponse/SAMLRequest bodies, JWTs, session cookies, OAuth codes, access/refresh tokens.
- Private keys, signing secrets, full IdP metadata endpoints and authenticated session URLs.
- Real names/emails, phone numbers, addresses, or other personal data beyond lab personas.
- Screenshots showing live account administration controls, tenant details, or browser address bars.

If a screenshot needs sanitization, use **solid opaque masks or safe cropping** rather than translucent blur. Verify no secret remains in image metadata, filename, alt text, or nearby prose. Assume published screenshots remain permanently discoverable.

**Limitations:** The supplied images were visually reviewed and selected, but automated screening cannot guarantee every possible secret is detected. Conduct a final manual check before setting a repository public. Keep original unsanitized evidence **outside** GitHub.

**Demonstration-only apps:** Finance and HR bookmarks show assignment and visibility; they are not real protected finance/HR resources.
