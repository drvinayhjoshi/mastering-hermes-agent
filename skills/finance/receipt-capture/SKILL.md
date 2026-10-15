---
name: receipt-capture
description: Logs a receipt photo to the expenses file and folder
version: 1.2.0
metadata:
  hermes:
    tags: [finance, expenses, playbook-02]
    category: finance
---

# Receipts captured by photograph

## When to Use
When I send a photo that looks like a receipt or bill.

## Procedure
1. Extract merchant, date, total, tax amount, currency.
2. Choose a category from: travel, meals, fuel, supplies,
   software, professional fees, other.
3. Append to ~/Business/Expenses/expenses.csv.
4. Save the image as receipts/YYYY-MM-DD-merchant.jpg.
5. Reply with merchant, total, category on one line.

## Pitfalls
- Faded thermal receipts: if the total is unreadable, say so and
  ask, rather than guessing a number.
- Tips written by hand are often not in the printed total.
- Foreign-currency receipts: record the original currency, do
  not convert.

## Verification
Re-read the appended row and confirm the total matches what is
printed on the image.

## Stop and Ask Me Instead When
- The receipt looks like a large asset or a warranty item. Log
  it as usual, then remind me to keep the paper original.
- You cannot read the total or the date. Ask me for a clearer
  photo; never guess.

## Approval Required
Reply to me with merchant, total and category for every receipt
so I can check it. Never send, pay, post or delete anything
without my explicit "approved".
