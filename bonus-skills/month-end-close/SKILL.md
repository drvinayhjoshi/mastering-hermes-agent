---
name: month-end-close
description: "The month-end close that doesn't take three days (Mastering Hermes Agent, bonus skill)"
version: 1.0.0
metadata:
  hermes:
    tags: [finance, bonus]
    category: finance
---

# The month-end close that doesn't take three days

## When to Use
When I ask for the month-end pack, the month-end checklist,
or what my bookkeeper still needs for last month.

## Procedure
1. Collect last month's bank statement export, the sales
   invoices issued, the supplier bills in the payables
   register, and the receipts in expenses.csv.
2. Match each bank transaction to an invoice, a bill or a
   receipt. Do the matching with a script, not by eye.
3. List: unmatched transactions, documents with no matching
   transaction, missing receipts, duplicate documents, and any
   charge outside the supplier's usual range.
4. Summarise receivables and payables outstanding at month end.
5. Save the pack to ~/Business/Finance/close/YYYY-MM/ and send
   me a one-page checklist for my bookkeeper.

## Pitfalls
- This prepares a close; it is not an accounting entry. Never
  post, adjust or delete anything in the accounting system.
- A transaction that matches two documents is an exception,
  not a match. List it.
- Card and bank fees rarely have a document. Group them, and
  don't report each one as a missing receipt.
- Never guess a missing amount or date.

## Verification
Transactions read = matched + unmatched. Documents read =
matched + unmatched. Show both sums.

## Stop and Ask Me Instead When
- The month includes a loan, an asset purchase, a write-off or
  anything else unusual. My bookkeeper handles those.
- The bank export covers a different period from the documents.

## Approval Required
The pack comes to me and my bookkeeper. My bookkeeper posts
every entry. Never send, pay, post or delete anything without
my explicit "approved".

<!--
Example of what comes back:
  MONTH-END · September
  214 transactions reviewed · 207 matched
  3 unmatched (listed) · 2 missing receipts · 1 duplicate bill
  1 unusual charge: Kiran Electricals 41,000 (usual 9-12,000)
  Receivables outstanding: 6 invoices · Payables: 9 bills
Adjust every folder path above to match where your files actually live.
-->
