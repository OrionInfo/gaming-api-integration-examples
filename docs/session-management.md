# Session management

A launch flow commonly creates a short-lived session reference that connects a player to an external service.

## Example sequence
1. The player is authenticated by the platform.
2. The backend verifies eligibility and creates a scoped session.
3. The backend sends a launch request using a server-side credential.
4. The provider returns a launch URL or session reference.
5. The platform applies expiry, logout, and revocation rules.

## Session safety
- Use opaque, high-entropy identifiers.
- Keep sessions short-lived and scoped.
- Do not put personal data or wallet secrets in launch URLs.
- Enforce server-side expiry and revocation.
- Avoid logging full session tokens.
- Validate return URLs against an allowlist.

A browser redirect alone must not be treated as proof of identity or transaction completion.
