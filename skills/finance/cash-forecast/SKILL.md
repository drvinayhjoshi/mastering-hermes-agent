---
name: cash-forecast
description: Four-week cash forecast; flags weeks below the floor
version: 1.2.0
metadata:
  hermes:
    tags: [finance, cash-flow, playbook-03]
    category: finance
---

# Knowing your cash position on a Monday

## When to Use
When I ask for the cash forecast, the Monday cash, or where the
bank balance is heading.

## Procedure
1. Read this week's balance and its date from
   ~/Business/Finance/balance.md.
2. Read the open invoices in ~/Business/Invoices/Open and, for
   each client, apply their observed payment timing from memory.
3. Read the committed outgoings in
   ~/Business/Finance/commitments.md.
4. Lay out four weeks: opening balance, in, out, closing.
5. Flag any week that closes below ₹200,000.
6. Name the single receipt that would most change the picture.

## Pitfalls
- Stated terms are not payment behaviour. Use observed history
  per client; if there is none, use terms plus 10 days.
- Payroll and rent in the same week is the usual failure point —
  check for date collisions explicitly.
- Do not treat a disputed invoice as an expected receipt.
  Anything flagged in disputes.md is excluded.

## Verification
Week 1 closing balance must equal opening plus receipts minus
commitments. State the arithmetic in the output.

## Stop and Ask Me Instead When
- The balance in balance.md is more than 7 days old, or
  commitments.md has not changed in over a month. Say so at the
  top and ask me to update it before you forecast.
- I mention hiring, borrowing or a large purchase. Add a line
  telling me to check the figures with my bank and my accountant
  before I decide.

## Approval Required
None; this report comes to me only. Never send, pay, post or
delete anything without my explicit "approved".
