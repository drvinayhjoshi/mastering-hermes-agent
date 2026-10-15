---
name: payables
description: Logs supplier bills; flags duplicates, bank changes
version: 1.2.0
metadata:
  hermes:
    tags: [finance, payables, playbook-04]
    category: finance
---

# Supplier bills, never missed and never paid twice

## When to Use
When I ask about supplier bills, what we owe, what is due this
week, or for the payables list.

## Procedure
1. Read new files in ~/Business/Payables/Inbox. Extract
   supplier, invoice number, date, amount, tax, due date, bank
   details. Append to register.csv; move nothing.
2. Check duplicates against the register (same supplier and
   number, number plus a suffix, or same amount within 30 days).
3. Compare with the supplier's range in suppliers.md, and match
   to a purchase order where the supplier requires one.
4. Compare bank details with the supplier's previous bill.
5. Produce: needs a look, due in 7 days, overdue, ageing.

## Pitfalls
- Never pay, schedule a payment, or reply to a supplier.
- Changed bank details are the classic invoice fraud. Always
  flag them, and never take the new details from the email that
  announced the change.
- A credit note is a negative bill. Net it against the same
  supplier before listing what is due.
- If a field can't be read, flag the bill. Do not guess a due
  date.

## Verification
Bills read = rows added + bills flagged unreadable. State the
total due in 7 days and show the addition.

## Stop and Ask Me Instead When
- A supplier's email says their bank details have changed. Put
  it at the top and tell me to verify by phone on a number I
  already hold. Never update the details yourself.
- A bill is marked disputed, or the goods have not arrived. List
  it under "needs a look", not under "due".
- It is the first bill from a supplier not in suppliers.md. List
  it under "needs a look" so I check it once.

## Approval Required
Never pay, schedule a payment, or contact a supplier. I approve
and pay every bill myself. Never send, pay, post or delete
anything without my explicit "approved".
