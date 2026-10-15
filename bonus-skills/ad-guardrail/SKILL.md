---
name: ad-guardrail
description: "The ad spend guardrail (Mastering Hermes Agent, bonus skill)"
version: 1.0.0
metadata:
  hermes:
    tags: [marketing, bonus]
    category: marketing
---

# The ad spend guardrail

## When to Use
When I ask for the ad check or whether any campaign
is overspending.

## Procedure
1. Read the latest daily export in ~/Business/Marketing/ads/.
2. Flag any campaign spending over 150% of its daily budget pace.
3. Flag any whose cost per conversion is over twice our target.
4. Flag any that has spent over ₹5,000 with no conversions.
5. If nothing breaches, reply with one line only.

## Pitfalls
- Conversions report late on most platforms. Do not flag
  zero conversions on spend less than 48 hours old.
- Weekend pace differs from weekday. Compare like with like.
- Never pause, edit or change a campaign. Report only.

## Verification
State the date range of the data read, so stale exports
are obvious.

## Approval Required
None; report only. Never pause, edit or change a campaign.

<!--
Risk: Low.
Original instruction from the book:
"Read the daily export in ~/Business/Marketing/ads/. Tell me: anything spending more than 150% of its daily budget pace, anything whose cost per conversion is more than twice our target, and anything that has spent over ₹5,000 with no conversions at all. If none of those are true, reply with one line and nothing else."
Adjust every folder path above to match where your files actually live.
-->
