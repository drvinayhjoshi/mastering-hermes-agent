---
name: reorder
description: Suggests reorders and drafts POs from stock and sales
version: 1.7.0
metadata:
  hermes:
    tags: [operations, inventory, playbook-22]
    category: operations
---

# Reordering before you run out

## When to Use
When I ask what to reorder, about stock levels, or for draft
purchase orders.

## Terms
- ROP (reorder point): the stock level at which I must reorder.
- MOQ (minimum order quantity): the smallest order a supplier
  accepts.
- Pack size: the multiple a supplier sells in (a pack of 10).
- On order: already ordered, not yet delivered.

## How the numbers are worked out
Daily sales = the larger of (units sold in the last 56 days,
units sold in the same 56 days last year), divided by 56. ROP =
daily sales x (lead time days + safety days). If on hand + on
order is at or below ROP, the order is ROP + 30 x daily sales -
(on hand + on order), rounded up to a whole pack, and raised to
the MOQ if lower. Example: 56 units in 56 days is 1 a day. Lead
time 14, safety 3: ROP 17. On hand 10: order 17 + 30 - 10 = 37,
rounded to a pack of 10 gives 40.

## Procedure
1. Load stock.csv, the sales file, suppliers.md and my notes
   (~/Business/notes.md). Match on item code. An item code that
   is not in the sales file gets no quantity: list it.
2. Do the arithmetic with the script below. Do not do it by
   hand. Save it as reorder_calc.py, edit only the lines marked
   EDIT, and run it in the terminal with python3
   reorder_calc.py. What to edit: ROOT is the folder that holds
   my files, for example ROOT = "/home/me/Business"; SAFETY
   lists each supplier's safety days from suppliers.md; FLAG
   lists the suppliers my notes say are changing, on promotion
   or discontinued, for example FLAG = {"VinylCo"}. The first
   lines of your reply are the script's output, in a code block,
   unchanged. Write nothing before it. If you cannot run it,
   say so and give no quantities.
3. Items the script prints as FLAGGED (a supplier change,
   promotion, discontinued line, or a perishable or expiring
   item) get no order quantity and never appear on any draft
   purchase order. List them, with their supplier.
4. For the other items, use the script's order quantity as it
   stands. If any order is more than 10 times A in the script's
   output (A is the units sold in the last 56 days), the figures
   are probably wrong: recheck, and if it still holds, move the
   item to the FLAGGED list.
5. Slow stock: the script prints items with stock on hand and no
   sales for 120 days or more. An item with nothing on hand is
   out of stock, not slow.
6. Draft one purchase order per supplier from the unflagged
   items that have an order quantity. Do not send. If a draft is
   above the order value that suppliers.md says needs
   negotiating, mark it "starting point for negotiation". If you
   do not know the total, do not mark it.
7. After the code block, write the FLAGGED list, then the draft
   orders. A reply that is only the code block is incomplete.

```python
import csv, math, os
# EDIT THESE LINES to match your files and notes
ROOT = os.path.expanduser("~/Business")
STOCK = ROOT + "/Finance/stock.csv"  # code,item,on_hand,on_order,pack_size,moq,lead_days,supplier,perishable
SALES = ROOT + "/Finance/sales-12m.csv"  # code,last8w_units,same8w_last_year_units,days_since_last_sale
SAFETY = {"BrightSupply": 3, "VinylCo": 2, "AcrylicHub": 5}  # safety days per supplier
FLAG = {"VinylCo"}  # suppliers my notes say are changing, on promotion or discontinued
DAYS = 56           # 8 weeks

sales = {r["code"]: r for r in csv.DictReader(open(SALES))}
stock = list(csv.DictReader(open(STOCK)))
for r in stock:
    code, sup = r["code"], r["supplier"]
    if sup in FLAG or r["perishable"].strip().lower().startswith("yes"):
        print(f"{code} {r['item']} | supplier {sup} | FLAGGED, no quantity")
        continue
    if code not in sales:
        print(f"{code} {r['item']} | supplier {sup} | NOT IN SALES FILE, no quantity")
        continue
    s = sales[code]
    a, b = float(s["last8w_units"]), float(s["same8w_last_year_units"])
    daily = max(a, b) / DAYS
    rop = daily * (int(r["lead_days"]) + SAFETY[sup])
    have = int(r["on_hand"]) + int(r["on_order"])
    if have > rop:
        print(f"{code} {r['item']} | supplier {sup} | A={a:g} B={b:g} daily={daily:.3f} ROP={rop:.2f} have={have} | no order")
        continue
    need = rop + 30 * daily - have
    qty = max(math.ceil(need / int(r["pack_size"])) * int(r["pack_size"]), int(r["moq"]))
    print(f"{code} {r['item']} | supplier {sup} | A={a:g} B={b:g} daily={daily:.3f} ROP={rop:.2f} have={have} need={need:.1f} -> order {qty}")
print("NO SALES FOR 120 DAYS OR MORE, STOCK ON HAND:")
slow = [r for r in stock if r["code"] in sales and int(sales[r["code"]]["days_since_last_sale"]) >= 120 and int(r["on_hand"]) > 0]
for r in slow:
    print(f"{r['code']} {r['item']} | on hand {r['on_hand']} | days since last sale {sales[r['code']]['days_since_last_sale']}")
if not slow:
    print("none")
```

## Pitfalls
- Count stock already on order. Ignoring it double-orders.
- Daily sales is units divided by days. A total of units over 8
  weeks is not a daily figure.
- Never place, send or confirm an order.

## Verification
Items checked = rows in stock.csv. The script's output is pasted
in the reply. No flagged item is on a draft order.

## Stop, or Flag, Instead of Ordering
- My notes mention a supplier change, a promotion or a
  discontinued line. Flag the affected items; do not size their
  orders by formula.
- An item is perishable or has an expiry date. Flag it and leave
  its quantity to me.

## Approval Required
Draft purchase orders only. Never place, send or confirm an
order. Never send, pay, post or delete anything without my
explicit "approved".
