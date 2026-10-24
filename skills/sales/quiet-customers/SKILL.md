---
name: quiet-customers
description: Lists customers overdue against their order rhythm
version: 1.6.0
metadata:
  hermes:
    tags: [sales, retention, playbook-11]
    category: sales
---

# Noticing the customer who went quiet

## When to Use
When I ask which customers have gone quiet or stopped ordering.

## Procedure
1. Read ALL my notes FIRST, before you look at any order: every
   notes file under ~/Business (for example ~/Business/notes.md
   and ~/Business/Sales/notes.md), and any open invoice file
   marked DISPUTED (look in ~/Business/Invoices/Open). Make a
   "left off" list of every customer with any of: a pause
   request (with its date), a dispute or disputed invoice, a
   complaint, a legal matter, a change of owner, a seasonal
   closure. Write the reason and the file it came from.
2. Read ~/Business/Sales/orders.csv. Do the arithmetic with a
   script if you can, not by eye, and show the numbers: for each
   customer work out the usual gap (the average number of days
   from one order to the next, from their own history), the days
   since their last order, and the total of their orders in the
   12 months up to today.
3. A customer is quiet when the days since their last order are
   more than 1.5 times their usual gap.
4. A customer on the "left off" list is NEVER in the main list,
   whatever their gap. Show them in a separate short list with
   the reason. They are not counted as quiet.
5. A customer with fewer than four orders has no reliable
   pattern. Do not put them in the main list. Name EVERY such
   customer in one line with their order count, even if they are
   also on the left-off list, in this shape: "Fewer than four
   orders: <customer> (<count>), <customer> (<count>)." Count the
   rows for each customer in orders.csv: list exactly the
   customers with 1, 2 or 3 rows, and do not guess.
6. Order the main list by the last-12-month total, largest
   first. Use the currency in orders.csv; if it has none, write
   the amounts with no currency name or sign, and write no
   sentence about currency or date format.
7. For each in the main list, say when they last ordered, what
   they usually buy, their usual gap and their current gap in
   days. Describe the gap; don't guess why.
8. If nobody qualifies for the main list, say so plainly ("No
   customers qualify") and still show the left-off list and the
   fewer-than-four line.

## Pitfalls
- Seasonal businesses look dormant every year at the same time.
  If my notes mention a seasonal closure, leave them off the
  main list.
- One large annual order is not a lapsed monthly customer.
- Report the pattern, never an intention. "Gap is 2.1 times
  their usual" is a finding; "about to leave" is a guess.
- If you did not read the notes files, say so and give no list.

## Verification
State each listed customer's usual gap and current gap, and the
total used for ordering. If any customer is on both lists,
remove them from the main list and say so. If the main list is
empty, the first line of the reply is "No customers qualify."
Attach a note, dispute or complaint to a customer only if the
file you read names that customer. Write amounts with a
currency name or sign only if orders.csv shows one. Do not
write any sentence about currency or date format.

## When You Find These
- My notes explain the gap: a dispute, a complaint, a change of
  owner, a seasonal closure. Leave the customer off the main
  list and show them under the left-off list.
- The customer asked for a pause. Leave them off until the date
  they gave.

## Approval Required
None; the list comes to me. Never contact a customer. Never
send, pay, post or delete anything without my explicit
"approved".
