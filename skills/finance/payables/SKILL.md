---
name: payables
description: Logs supplier bills; flags duplicates, bank changes
version: 1.8.0
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
1. Read new files in ~/Business/Payables/Inbox. For each bill,
   extract supplier, invoice number, date, amount, tax, due date
   and bank details. If a field cannot be read, flag the bill;
   do not guess a due date. Do not move, rename or delete the
   bill files.
2. Check every bill BEFORE you add it to register.csv:
   a. Duplicate: the same supplier and the same invoice number,
      the number plus a suffix (S-77 and S-77A), or the same
      supplier, amount and bill date.
   b. Bank change: the bank details differ from the supplier's
      previous bill or from suppliers.md, or the bill or email
      says they have changed.
   c. Needs a look: a bill marked disputed, goods not yet
      arrived, a first bill from a supplier not in suppliers.md,
      or an amount outside the supplier's usual range written in
      suppliers.md.
3. Net each credit note against the same supplier's bills. Do not
   add a credit note to the register as a bill.
4. Now add the rows to register.csv, and read the file back to
   check. Use only the columns in its header line. Add every
   bill that is NOT a duplicate, including a bill with a bank
   change. A duplicate is never added; list it with the bill it
   repeats. For a bank change, write CHANGED - UNVERIFIED in the
   bank column (or in a notes column if the register has one),
   and never write the new account number anywhere in the
   register. Count the new rows you read back: that count is the
   "added" number in step 6.
5. Write the reply in this order, with these headings (do not
   print the numbers), and write "none" under any that is empty:
   1. BANK DETAILS CHANGED: for each, write "<supplier>: new
      account details received. Verify by phone on a number you
      already hold." Write nothing more about the details;
      never repeat the new account number in the reply.
   2. NEEDS A LOOK: duplicates, disputed bills, first-time
      suppliers, unusual amounts, unreadable bills.
   3. OVERDUE
   4. DUE IN 7 DAYS
   5. AGEING: every unpaid bill, with its age in days
      counted from the bill date.
   The first line of the reply is the words BANK DETAILS
   CHANGED.
6. End the reply with one line in this shape, replacing every
   <...> with a real number from this run (no placeholder
   letters such as N, A, D or U): "CHECK: bills read <number> =
   added <number> + duplicates <number> + unreadable <number>.
   Due in 7 days: <amount of each bill due, joined by +> =
   <total>." If nothing is due, write "Due in 7 days: 0." The due
   figure must agree with heading 4.

## Pitfalls
- Never pay, schedule a payment, or reply to a supplier.
- Changed bank details are the classic invoice fraud. Always
  flag them at the top.
- A bill that is a duplicate must not appear under "due",
  "overdue" or "ageing", or the totals will count it twice.
- Do not say a bill was added unless you read it back from the
  register.

## Verification
The CHECK line adds up, and the number of rows added matches the
"added" number. The first line of the reply is BANK DETAILS
CHANGED.

## When You Find These
- A bank change is found. It goes under BANK DETAILS CHANGED,
  first in the reply. Never update the details yourself.
- A bill is marked disputed, or the goods have not arrived. List
  it under NEEDS A LOOK, not under due.
- It is the first bill from a supplier not in suppliers.md. List
  it under NEEDS A LOOK so I check it once.

## Approval Required
Never pay, schedule a payment, or contact a supplier. I approve
and pay every bill myself. Never send, pay, post or delete
anything without my explicit "approved".
