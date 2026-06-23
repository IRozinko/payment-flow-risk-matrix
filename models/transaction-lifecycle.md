# Transaction Lifecycle — Risk-Oriented View

## Lifecycle stages

1. User intent
2. Eligibility / limit check
3. Fee preview
4. Authorization / confirmation
5. Funds reservation
6. Provider / network submission
7. Pending state
8. Confirmation / failure / timeout
9. Ledger update
10. User-facing transaction history
11. Reconciliation / reporting

## Typical failure modes

- Fee preview differs from final fee
- Limits are checked before but not after state change
- Funds are reserved but never released
- Provider callback arrives late or out of order
- Retry creates duplicate operation
- UI shows confirmed while backend remains pending
- Reconciliation detects mismatch too late

## Test design prompts

- What happens if the provider never responds?
- What happens if the user retries?
- What happens if the callback arrives twice?
- What happens if the currency precision differs?
- What happens if the fee rule changes mid-flow?
- What state does support see?
