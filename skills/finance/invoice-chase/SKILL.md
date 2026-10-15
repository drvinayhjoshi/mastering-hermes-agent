---
name: invoice-chase
description: Drafts chase emails for overdue invoices, to me only
version: 1.2.0
metadata:
  hermes:
    tags: [finance, receivables, playbook-01]
    category: finance
---

# The invoice chase that actually happens

## When to Use
When I ask to chase invoices, about overdue accounts, or who
owes us money.

## Procedure
1. Read every file in ~/Business/Invoices/Open.
2. Select invoices more than 30 days past the due date.
3. Draft one email per client: invoice number, amount, original
   due date, a polite request, my payment details.
4. Send all drafts to me. Never send to a client directly.
5. List separately any invoice that could not be parsed.

## Pitfalls
- Credit notes appear as negative amounts; net them against the
  same customer before deciding who is overdue.
- Some clients have two names in the system (trading name and
  legal name). Group them.
- A blank due date means the invoice was never issued properly —
  flag it, don't chase it.

## Verification
The count of drafts plus the count of unparsed invoices should
equal the number of invoices over 30 days.

## Stop and Ask Me Instead When
- An invoice is marked disputed, or the client has complained
  about the work or goods. List it for me; do not draft a chase.
- My notes say the client is in financial difficulty, a legal
  dispute or a negotiation with us. List it for me instead.
- The client is one I have told you I handle personally, or the
  amount is large enough that I would phone. Flag it for a call.

## Approval Required
Send all drafts to me. Never send a chase email to a client.
Never send, pay, post or delete anything without my explicit
"approved".
