# Wallet callbacks and transaction integrity

Wallet callbacks are sensitive operations. The platform should remain authoritative for balances and transaction records.

## Example callback fields
```json
{
  "event_id": "evt_demo_1001",
  "transaction_id": "txn_demo_2001",
  "session_id": "sess_demo_3001",
  "operation": "debit",
  "amount_minor": 250,
  "currency": "USD"
}
```
All values are fictional. `amount_minor` represents integer minor units, avoiding floating-point currency arithmetic.

## Validation checklist
- Authenticate the sender (for example, a verified signature).
- Validate schema, currency, amount bounds, and session state.
- Enforce idempotency using a stable transaction or event ID.
- Apply balance changes atomically.
- Persist a durable result before acknowledging success.
- Reconcile retries and out-of-order events.
- Reject replayed, expired, or unauthorized requests.

Never trust a client-supplied balance or accept a callback solely because it arrived at a known URL.
