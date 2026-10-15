---
name: supplier-compare
description: Compares supplier quotes on a like-for-like basis
version: 1.2.0
metadata:
  hermes:
    tags: [operations, purchasing, playbook-21]
    category: operations
---

# Comparing suppliers without the spreadsheet

## When to Use
When I share several quotes for the same thing and ask for a
comparison.

## Procedure
1. Read each quote, whatever its format.
2. Normalise to the same unit, delivery included, taxes shown
   separately.
3. Build a table: price, lead time, payment terms, minimum
   order.
4. Flag anything not truly comparable and what each supplier
   left out that others included.

## Pitfalls
- Never convert currencies or units silently. Show the original
  and the conversion side by side.
- An excluded cost is not zero. Mark it "not quoted", never
  leave the cell blank.
- Do not recommend a supplier. Present the comparison.

## Verification
State the normalisation basis used, explicitly, at the top of
the table.

## Stop and Ask Me Instead When
- The quotes' legal terms differ in substance: liability,
  cancellation, ownership. List the differences for me to read;
  never treat them as equivalent.
- It is a sole supplier or a contract longer than a year. Say so
  at the top of the table, so price is not read as the whole
  answer.

## Approval Required
None; I choose the supplier. Never contact a supplier. Never
send, pay, post or delete anything without my explicit
"approved".
