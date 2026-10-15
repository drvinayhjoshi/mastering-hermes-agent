---
name: quiet-customers
description: Lists customers overdue against their order rhythm
version: 1.2.0
metadata:
  hermes:
    tags: [sales, retention, playbook-11]
    category: sales
---

# Noticing the customer who went quiet

## When to Use
When I ask which customers have gone quiet or stopped ordering.

## Procedure
1. Read ~/Business/Sales/orders.csv.
2. Work out each customer's normal ordering interval from their
   own history.
3. List anyone more than 1.5 times their usual gap without an
   order.
4. Order by annual revenue at risk.
5. For each, say when they last ordered, what they usually buy,
   and anything in my notes. Describe the gap; don't guess why.

## Pitfalls
- Seasonal businesses look dormant every year at the same time.
  Compare against the same period last year before flagging.
- A customer with fewer than four orders has no reliable
  pattern. Exclude them rather than guessing.
- One large annual order is not a lapsed monthly customer.
  Classify by cadence before measuring the gap.
- Report the pattern, never an intention. "Gap is 2.1 times
  their usual" is a finding; "about to leave" is a guess. Do not
  infer churn intent.

## Verification
State each customer's computed baseline alongside their current
gap, so the judgement is visible and arguable.

## Stop and Ask Me Instead When
- My notes already explain the gap: a dispute, a change of
  owner, a seasonal closure. Leave the customer off the list and
  count them as explained.
- The customer asked for a pause. Leave them off the list until
  the date they gave.

## Approval Required
None; the list comes to me. Never contact a customer. Never
send, pay, post or delete anything without my explicit
"approved".
