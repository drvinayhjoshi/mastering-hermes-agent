---
name: supplier-compare
description: Compares supplier quotes on a like-for-like basis
version: 1.8.0
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
1. Read each quote, whatever its format, including its terms.
2. Write the warnings first, each as a full sentence naming the
   supplier. Write each of these that applies:
   - SOLE SUPPLIER: when a quote says its supplier is the only
     source or the sole distributor. For example: "SOLE SUPPLIER: <supplier name> is the
     only source of this item."
   - LONG CONTRACT: when a contract is longer than a year. For
     example: "LONG CONTRACT: <supplier name> requires a
     <number>-month contract."
   - LEGAL TERMS DIFFER: when liability, cancellation or
     ownership terms differ in substance. Read the terms of every
     quote before you decide there are none, and name every kind
     of term that differs, not only one. For example: "LEGAL
     TERMS DIFFER: <supplier A> limits liability to the value of
     the goods and does not allow cancellation; <supplier B>
     accepts unlimited liability and allows cancellation."
3. Normalise to the unit most of the quotes use (for example one
   strip or one metre). Put delivery in its own column; do not
   add it to the price. Show tax exactly as each quote states it,
   using these exact words:
   - The quote does not say whether tax is included: write "tax
     not stated" and compare that quote on its stated price only.
   - The quote says tax is extra and gives no rate: write "tax
     extra, rate not given".
   - The quote includes tax at a rate that the quote itself
     states: you may work out the before-tax price from that
     rate. Round to two decimals in the normal way (12.346
     becomes 12.35). Write the word "calculated" in that same
     cell next to the number.
   Never use a tax rate that the quote does not state.
4. Build the table. For price, use two columns, "price before
   tax" and "price after tax", and no other price column. Do not
   use a single "unit price" column. If a quote says tax is extra
   and gives no rate, its "price after tax" cell says "tax extra,
   rate not given". If a quote gives only one of the two prices
   for any other reason, the other cell says "not stated". Then
   add delivery, lead time, payment terms and minimum order.
5. Flag anything not truly comparable and what each supplier left
   out that others included.
6. Write the reply in this order: the warnings from step 2 (or
   "No warnings"), then the basis line, then the table, then the
   flags. The basis line is one line that says which unit and
   which tax treatment the table uses, for example: "Basis: price
   per <unit>, in <currency>; tax as each quote states it." If
   the table shows totals for the whole order instead of a unit
   price, say so in the basis line. The warnings come first,
   above the table, as their own lines.

## Pitfalls
- Never convert currencies or units silently. If you convert,
  show the original and the converted value side by side.
- An excluded cost is not zero. Mark it "not stated", never
  leave the cell blank.
- Never put a tax-inclusive price and a tax-exclusive price in
  the same column.
- Do not recommend a supplier. Present the comparison.

## Verification
The basis line is at the top of the table. Check that every
warning from step 2 appears above the table, is a full sentence,
and says something, and that no column mixes before-tax and
after-tax prices.

## When You Find These
- The quotes' legal terms differ in substance: liability,
  cancellation, ownership. List the differences for me to read;
  never treat them as equivalent.
- It is a sole supplier or a contract longer than a year. Say so
  above the table, on its own line, so price is not read as the
  whole answer.

## Approval Required
None; I choose the supplier. Never contact a supplier. Never
send, pay, post or delete anything without my explicit
"approved".
