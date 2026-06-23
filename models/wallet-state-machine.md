# Wallet State Machine — Draft Model

## Core wallet states

| State | Meaning | Key risks |
|---|---|---|
| Available | Funds can be used | Stale balance, wrong currency precision |
| Reserved | Funds held for pending operation | Reservation not released, double reservation |
| Pending | Operation submitted but not final | User confusion, timeout mismatch |
| Confirmed | Operation finalized | Backend/UI mismatch |
| Failed | Operation failed | Funds not returned, wrong fee state |
| Reversed | Operation reverted | Ledger mismatch, duplicated reversal |
| Blocked | Wallet or operation restricted | Limit/compliance false positive |

## Transitions to test

- Available → Reserved
- Reserved → Pending
- Pending → Confirmed
- Pending → Failed
- Failed → Available
- Confirmed → Reversed
- Available → Blocked
- Blocked → Available

## Cross-cutting checks

- Idempotency
- Race conditions
- Retry behavior
- Provider callback ordering
- Ledger consistency
- UI state consistency
- Audit trail completeness
