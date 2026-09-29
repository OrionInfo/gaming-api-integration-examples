# Authentication

Use separate mechanisms for user-facing authentication and server-to-server API authentication.

## Recommended controls
- Prefer short-lived, scoped credentials or signed tokens.
- Store secrets in a managed secret store or environment configuration, never in source control.
- Rotate credentials and revoke compromised keys.
- Validate issuer, audience, expiry, signature, and permitted scope.
- Use TLS and avoid placing secrets in URLs.
- Redact authorization headers and tokens from logs.

## Placeholder example
`Authorization: Bearer EXAMPLE_TOKEN_DO_NOT_USE`

The string above is intentionally fictional and must never be accepted by a real service. Do not use hard-coded credentials in production.
