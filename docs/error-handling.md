# Error handling, retries, and idempotency

## Error contract
Return a stable machine-readable error code, a safe message, and a correlation ID. Avoid exposing stack traces, secrets, or internal topology.

## Retry guidance
- Retry transient network errors and selected 5xx responses with bounded exponential backoff and jitter.
- Do not blindly retry non-idempotent operations.
- Reuse the same idempotency key for retries of the same logical operation.
- Set connection and response timeouts.
- Use a dead-letter or reconciliation process for unresolved events.

## Example error
```json
{
  "error": {
    "code": "SESSION_EXPIRED",
    "message": "The session is no longer active.",
    "correlation_id": "corr_demo_4001"
  }
}
```
