---
name: obligations
description: Daily check of compliance deadlines, by consequence
version: 1.2.0
metadata:
  hermes:
    tags: [operations, compliance, playbook-24]
    category: operations
---

# The compliance and deadlines calendar

## When to Use
When I ask what is due, about deadlines, or for the obligations
check.

## Procedure
1. Read the table in ~/Business/Admin/obligations.md.
2. List every row inside its notice period: what it is, the
   deadline, days left, the consequence if missed, the owner,
   and my first action.
3. Order by consequence, not by date.
4. List separately any row with no due date or no consequence.
5. If nothing is due, say "nothing due" explicitly.

## Pitfalls
- Order by consequence, not by date. A high-consequence item
  three weeks out outranks a trivial one due tomorrow.
- An obligation with no recorded consequence is treated as high
  until I say otherwise.
- Do not stop alerting because you alerted yesterday. Repeat
  daily inside the notice period until marked done.

## Verification
State the total number of obligations tracked, so a truncated
read is obvious.

## Stop and Ask Me Instead When
- obligations.md has no "last reviewed" date, or it is more than
  a year old. Say so first, and remind me to review the file
  with my adviser; rules and thresholds change.
- Something is due to be filed or paid. Alert me; never file,
  submit or pay it yourself.

## Approval Required
None; alerts come to me. Never file or pay anything. Never send,
pay, post or delete anything without my explicit "approved".
