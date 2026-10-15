---
name: competitor-watch
description: "Watching what competitors charge (Mastering Hermes Agent, bonus skill)"
version: 1.0.0
metadata:
  hermes:
    tags: [sales, bonus]
    category: sales
---

# Watching what competitors charge

## When to Use
When I ask what competitors have changed, or to
check the watchlist.

## Procedure
1. Fetch each page listed in ~/Business/Market/watchlist.md.
2. Save a dated copy to ~/Business/Market/snapshots/.
3. Compare with the previous snapshot.
4. Report only price, plan, feature and positioning changes.
5. If nothing changed, say so in one line.

## Pitfalls
- Marketing sites change wording constantly. Report only
  price, plan, feature and positioning changes; ignore
  copy edits and layout.
- A page that fails to load is not an unchanged page.
  Report fetch failures explicitly.
- Respect the site: one fetch per page per run, no more.

## Verification
State the date of the snapshot compared against. If there
is no prior snapshot, say "baseline captured" and stop.

## Approval Required
None; this report comes to me only.

<!--
Risk: Low.
Original instruction from the book:
"Check each page listed in ~/Business/Market/watchlist.md. Save a copy of what you find to ~/Business/Market/snapshots/ with today's date. Compare against the last snapshot. Tell me only what changed: prices, plan names, features added or removed, anything about positioning. If nothing changed, say so in one line."
Adjust every folder path above to match where your files actually live.
-->
