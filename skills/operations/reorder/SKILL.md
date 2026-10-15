---
name: reorder
description: Suggests reorders and drafts POs from stock and sales
version: 1.2.0
metadata:
  hermes:
    tags: [operations, inventory, playbook-22]
    category: operations
---

# Reordering before you run out

## When to Use
When I ask what to reorder, about stock levels, or for draft
purchase orders.

## Procedure
1. Load stock.csv, 12 months of sales, suppliers.md. Match on
   item code; list any item that fails to match.
2. With a script: daily sales = max(last 8 weeks, same 8 weeks
   last year). ROP = daily x (lead time + safety days).
3. Items with (on hand + on order) <= ROP: order enough to reach
   ROP + 30 days' sales, rounded up to pack size and MOQ.
4. List items with no sales in 120 days, with value at cost.
5. Draft one purchase order per supplier. Do not send.

## Pitfalls
- Count stock already on order. Ignoring it double-orders.
- An item that sold nothing because it was out of stock is not a
  slow seller. Check for zero stock before calling it dead.
- Never place, send or confirm an order.

## Verification
Items checked = rows in stock.csv. For each suggested order,
show daily sales, lead time, safety days, ROP and rounding.

## Stop and Ask Me Instead When
- My notes mention a supplier change, a promotion or a
  discontinued line. Flag the affected items and do not size
  their orders by formula.
- An item is perishable or has an expiry date. Flag it and leave
  its quantity to me.
- A draft order is above the value I have told you needs
  negotiating. Mark it "starting point for negotiation".

## Approval Required
Draft purchase orders only. Never place, send or confirm an
order. Never send, pay, post or delete anything without my
explicit "approved".
