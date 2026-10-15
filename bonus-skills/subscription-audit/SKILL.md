---
name: subscription-audit
description: "The subscription audit that pays for itself (Mastering Hermes Agent, bonus skill)"
version: 1.0.0
metadata:
  hermes:
    tags: [finance, bonus]
    category: finance
---

# The subscription audit that pays for itself

## When to Use
When I ask about subscriptions, recurring charges,
or what we are paying for every month.

## Procedure
1. Read the statements in ~/Business/Finance/statements/.
2. Find every charge that repeats monthly or annually.
3. For each: merchant, amount, frequency, start date, and
   whether the amount has changed.
4. Flag probable duplicates, rises of more than 15%, and
   anything I haven't mentioned before.
5. Produce one table sorted by annual cost, with a total, and
   end with a numbered list of candidates to cancel.

## Pitfalls
- The same vendor appears under several descriptors
  (e.g. "ACME*SUB", "ACME LTD", "ACME.IO"). Cluster by
  fuzzy match, then confirm.
- Annual charges look like one-offs in a 12-month window.
  Treat any charge that appears exactly once, twelve months
  apart, as annual.
- A price rise mid-year shows as two different amounts for
  the same merchant. That is a rise, not two subscriptions.

## Verification
The sum of all identified recurring charges should be
stated, and should be less than total spend. If it isn't,
the clustering has over-matched.

## Approval Required
None; I decide what to cancel. Never cancel anything yourself.

<!--
Risk: Low.
Original instruction from the book:
"Read the statements in ~/Business/Finance/statements/. Find every charge that repeats monthly or annually. For each, give me the merchant, the amount, the frequency, when it started, and whether the amount has changed. Flag anything that looks like a duplicate of another line, anything that increased by more than 15%, and anything I haven't mentioned to you before."
Adjust every folder path above to match where your files actually live.
-->
