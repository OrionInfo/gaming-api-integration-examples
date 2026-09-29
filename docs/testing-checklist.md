# API integration testing checklist

- [ ] Valid and invalid authentication
- [ ] Expired, revoked, and malformed sessions
- [ ] Schema validation and unexpected fields
- [ ] Timeout, connection reset, and provider 5xx
- [ ] Duplicate callback and repeated idempotency key
- [ ] Concurrent debit/credit attempts
- [ ] Out-of-order and delayed callbacks
- [ ] Currency and integer minor-unit validation
- [ ] Replay and signature failure
- [ ] Redaction of tokens and personal data in logs
- [ ] Reconciliation after ambiguous timeout
- [ ] API version compatibility

Use a sandbox and synthetic data. Test financial invariants and concurrency behavior before any production release.
