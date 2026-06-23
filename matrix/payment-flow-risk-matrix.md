# Payment Flow Risk Matrix

| Area | Risk | Example failure | Controls |
|---|---|---|---|
| Balance | Incorrect available balance | Pending transaction not reserved | Ledger checks, state tests, reconciliation |
| Fees | Wrong fee calculation | Tier/rule mismatch | Fee scenarios, boundary tests, fixtures |
| Limits | Limit bypass or false block | Daily/monthly counters stale | Limit matrix, concurrency tests |
| Currency | Rounding or FX error | Minor units mismatch | Currency fixtures, precision checks |
| Status | User sees wrong state | Provider callback delayed | State-machine tests, event replay |
| Retry | Duplicate charge | Retry is not idempotent | Idempotency keys, duplicate tests |
| Reversal | Money not returned | Failed transaction stays reserved | Reversal scenarios, ledger assertions |
| Web3 | Transaction state mismatch | Explorer confirmed, app pending | RPC/explorer comparison, timeout policy |
