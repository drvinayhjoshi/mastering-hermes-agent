---
name: month-end-close
description: "The month-end close that doesn't take three days (Mastering Hermes Agent, bonus skill)"
version: 1.5.0
metadata:
  hermes:
    tags: [finance, bonus]
    category: finance
---

# The month-end close that doesn't take three days

## When to Use
When I ask for the month-end pack, the month-end checklist,
or what my bookkeeper still needs for last month.

## Terms
- Pack: the file you save and the checklist you send me.
- Median: the middle value of a supplier's earlier charges.
- Exception: a bank transaction that matches two or more
  documents, so it cannot be matched with confidence.
- Not classified: left for my bookkeeper; you do not decide what
  it is.

## Procedure
1. Collect last month's bank statement export, the sales
   invoices issued, and the supplier bills. Earlier months' bank
   statements are in Finance/statements. Compare the first and
   last dates in the bank export with the month you are closing
   (MONTH in the script). If they do not match, stop and tell
   me.
2. Do the matching and the checks with the script below. Do not
   do them by hand. Save it as close_check.py, edit only the
   lines marked EDIT (the folder, the month, the file names),
   and run it in the terminal with python3 close_check.py. Paste
   its output into the pack before anything else. If you cannot
   run it, say so and give no totals.
3. Use the script's output as it stands:
   - FOR THE BOOKKEEPER, NOT CLASSIFIED: a loan payment, asset
     purchase, write-off or similar. Put these at the top of the
     pack. Do not classify, explain or total them, and do not
     call them fees.
   - UNUSUAL CHARGE: a charge more than 3 times that supplier's
     usual (median) amount from earlier months. Report both
     figures.
   - A transaction that matches two documents is an exception,
     not a match. List it, and list duplicate documents.
4. Also list the unmatched transactions and the documents with no
   matching transaction; the script prints both. The script does
   not check receipts. Write "receipts not checked" in the pack.
5. Fees: group only the lines the statement itself labels as bank
   or card fees. Never work out or invent a fee total.
6. Receivables and payables at month end: copy the script's
   RECEIVABLES OUTSTANDING and PAYABLES OUTSTANDING lines into
   the pack, unchanged. Add no currency sign unless the files
   show one.
7. Save the pack to ~/Business/Finance/close/YYYY-MM/pack.md,
   creating the YYYY-MM folder, and send me a one-page checklist
   for my bookkeeper. Begin every checklist line with the word
   "Review", then the item's name and amount. In the checklist
   only, never write "post", "posted", "posting", "as-is" or
   "ready to post", and never tell anyone to post, pay or delete.

```python
import csv, glob, os, statistics
# EDIT THESE LINES to match your files
ROOT = os.path.expanduser("~/Business")
MONTH = "2026-09"
BANK = f"{ROOT}/Finance/close/bank-{MONTH}.csv"  # date,desc,amount
BILLS = f"{ROOT}/Finance/close/bills-{MONTH}.csv"  # bill,supplier,amount
INVOICES = f"{ROOT}/Finance/close/invoices-issued-{MONTH}.csv"  # invoice,client,amount
STATEMENTS = ROOT + "/Finance/statements/*.csv"  # date,description,amount
SPECIAL = ("loan", "emi", "asset", "write-off", "writeoff")  # leave to the bookkeeper

bank = list(csv.DictReader(open(BANK)))
docs = [("bill", r["bill"], r["supplier"], abs(float(r["amount"]))) for r in csv.DictReader(open(BILLS))]
docs += [("invoice", r["invoice"], r["client"], abs(float(r["amount"]))) for r in csv.DictReader(open(INVOICES))]

used = set()
matched = exception = unmatched = 0
print("FOR THE BOOKKEEPER, NOT CLASSIFIED:")
for t in bank:
    if any(w in t["desc"].lower() for w in SPECIAL):
        print(f"  {t['date']} {t['desc']} {t['amount']}")
print("TRANSACTIONS:")
for t in bank:
    amt, d = abs(float(t["amount"])), t["desc"].lower()
    cand = [i for i, x in enumerate(docs) if x[3] == amt and (x[2].lower() in d or x[1].lower() in d)]
    if len(cand) == 1:
        matched += 1; used.add(cand[0]); status = f"matched {docs[cand[0]][1]}"
    elif len(cand) > 1:
        exception += 1; used.update(cand); status = "EXCEPTION, matches " + ", ".join(docs[i][1] for i in cand)
    else:
        unmatched += 1; status = "UNMATCHED"
    print(f"  {t['date']} {t['desc']} {t['amount']} -> {status}")
print(f"Transactions read {len(bank)} = matched {matched} + exceptions {exception} + unmatched {unmatched}")
nomatch = [docs[i] for i in range(len(docs)) if i not in used]
print("DOCUMENTS WITH NO TRANSACTION:", [(x[0], x[1], x[2], x[3]) for x in nomatch])
ids = [x[1] for x in docs]
print("DUPLICATE DOCUMENTS:", sorted({i for i in ids if ids.count(i) > 1}))
print(f"Documents read {len(docs)} = used {len(used)} + no transaction {len(nomatch)}")
unpaid = [x for i, x in enumerate(docs) if i not in used]
inv = [x for x in unpaid if x[0] == "invoice"]
bil = [x for x in unpaid if x[0] == "bill"]
print(f"RECEIVABLES OUTSTANDING: {len(inv)} invoices, total {sum(x[3] for x in inv):g}:", [x[1] for x in inv])
print(f"PAYABLES OUTSTANDING: {len(bil)} bills, total {sum(x[3] for x in bil):g}:", [x[1] for x in bil])
earlier = {}
for f in glob.glob(STATEMENTS):
    if MONTH in f:
        continue
    for r in csv.DictReader(open(f)):
        earlier.setdefault(r["description"].lower(), []).append(abs(float(r["amount"])))
print("UNUSUAL CHARGE:")
found = False
for t in bank:
    if float(t["amount"]) < 0 and t["desc"].lower() in earlier:
        usual = statistics.median(earlier[t["desc"].lower()])
        if abs(float(t["amount"])) > 3 * usual:
            found = True
            print(f"  {t['desc']} {abs(float(t['amount'])):g} (usual about {usual:g}, from {len(earlier[t['desc'].lower()])} earlier charges)")
if not found:
    print("  none")
print("LINES LABELLED AS FEES:", [t["desc"] for t in bank if "fee" in t["desc"].lower()] or "none")
```

## Pitfalls
- This prepares a close; it is not an accounting entry. Never
  post, adjust or delete anything in the accounting system. My
  bookkeeper posts the entries; the rule against the word
  "post" applies to your checklist text only.
- Never guess a missing amount or date. Never change a date or
  an amount you were given.
- Never describe an item as a fee, a loan fee or any other
  category unless the statement says so.
- Use only the numbers from the script and the files.

## Verification
The script's output is pasted in the pack, including the
receivables and payables lines. Transactions read = matched +
exceptions + unmatched, and documents read = used + no
transaction; all of these come from the script. Every checklist
line begins with "Review".

## When You Find These
- The month includes a loan, an asset purchase, a write-off or
  anything else unusual. List it under "FOR THE BOOKKEEPER, NOT
  CLASSIFIED" and leave it. My bookkeeper handles those.
- The bank export covers a different period from the documents.
  Stop and tell me.

## Approval Required
The pack comes to me and my bookkeeper. My bookkeeper posts
every entry. Never send, pay, post or delete anything without
my explicit "approved".
