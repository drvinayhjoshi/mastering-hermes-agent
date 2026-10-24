---
name: receipt-capture
description: Logs a receipt photo to the expenses file and folder
version: 1.8.0
metadata:
  hermes:
    tags: [finance, expenses, playbook-02]
    category: finance
---

# Receipts captured by photograph

## When to Use
When I send a photo that looks like a receipt or bill.

## Procedure
1. Extract merchant, date, total, tax amount, currency. If the
   total or the date cannot be read, stop here: write nothing
   and ask me for a clearer photo.
2. Choose a category from: travel, meals, fuel, supplies,
   software, professional fees, other.
3. Set the paper-original flag. It is YES if any of these is
   true: the receipt shows a warranty or guarantee period or a
   serial number; the item is a computer, a phone, a machine, an
   item of furniture, or a part for a vehicle; or the total is
   above 20,000 in my currency (edit this number to suit me).
   Otherwise NO.
4. Append one row to ~/Business/Expenses/expenses.csv, using the
   columns of its header line. For example, the header line may
   be: date,merchant,total,tax,currency,category
   In the file, write the total and the tax as plain numbers
   with two decimals and no commas (for example 1234.50), with
   no currency name in those columns. If the receipt shows no
   tax, write 0.00. Put the three-letter currency code (for
   example INR or USD) in the currency column. Put each value
   under its own column. Write the merchant as printed on the
   receipt; if the printed name has a comma, leave the comma out.
5. Save the image as
   ~/Business/Expenses/receipts/YYYY-MM-DD-merchant.jpg. In the
   file name only, use lowercase letters and hyphens, with no
   spaces, capitals or other punctuation. Everywhere else write
   the merchant as printed.
6. Check your work: confirm that the row was added to
   expenses.csv and that the image is in the receipts folder. If
   either is missing, say so in your reply.
7. Reply with merchant, total and category on one line, with
   exactly two commas, in this shape: <merchant as printed>,
   <currency> <total>, <category>. Write the total with no
   thousands comma (for example USD 1234.50). If the flag is YES,
   add a second line, word for word: "Keep the paper original:
   this looks like a warranty or large-asset item."

## Pitfalls
- Faded thermal receipts: if the total is unreadable, say so and
  ask, rather than guessing a number.
- Tips written by hand are often not in the printed total. Use
  the printed total and tell me a tip may be missing.
- Foreign-currency receipts: record the original currency, do
  not convert.

## Verification
The appended row shows the printed total, the image file exists,
and, if the flag is YES, your reply has the second line.

## When You Find These
- The total or the date cannot be read: stop as step 1 says.
- The flag in step 3 is YES. Do not stop: log it as usual, then
  give the second line of step 7.

## Approval Required
Reply to me with merchant, total and category for every receipt,
in the shape given in step 7, so I can check it. Never send, pay, post or delete anything
without my explicit "approved".
