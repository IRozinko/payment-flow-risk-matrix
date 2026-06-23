# Fee Service Test Scenarios

## Rule selection

- Correct fee rule selected by user segment
- Correct fee rule selected by product type
- Correct fee rule selected by currency
- Correct fee rule selected by transaction type
- Fallback rule behavior is explicit

## Boundary values

- Minimum amount
- Maximum amount
- Just below limit
- Exactly at limit
- Just above limit
- Zero and invalid amount handling

## Precision

- Minor units are respected
- Rounding mode is documented
- Cross-currency calculation is deterministic
- Displayed fee matches charged fee

## State and timing

- Fee preview equals final fee when conditions do not change
- Fee changes are handled between preview and execution
- Failed transaction does not charge fee unless intended
- Reversal/rollback handles fee correctly

## User-facing behavior

- Fee is visible before confirmation
- Error message is clear when fee cannot be calculated
- Fee details are traceable in transaction history
