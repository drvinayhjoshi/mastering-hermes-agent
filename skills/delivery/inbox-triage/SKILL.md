---
name: inbox-triage
description: Sorts unread mail into tiers; drafts routine replies
version: 1.2.0
metadata:
  hermes:
    tags: [delivery, email, playbook-17]
    category: delivery
---

# Inbox triage with drafts attached

## When to Use
When I ask you to triage the inbox or go through unread mail.

## Procedure
1. Read the unread mail.
2. Sort each message into urgent, needs me, routine or ignore,
   using my rules in support-rules.md.
3. For routine, draft a reply from
   ~/Business/Support/standard-answers.md.
4. For needs-me, give one line and the decision wanted.
5. Put urgent first, with the reason.

## Pitfalls
- A complaint is never routine, however politely it is worded.
  Route it to needs-me at minimum.
- Anything mentioning a legal matter, a regulator, or a refund
  over the threshold in support-rules.md goes urgent regardless
  of tone.
- Do not draft from standard-answers.md if the question is only
  similar. Similar is not the same; route it to me.

## Verification
Every message is in exactly one tier and the counts add up to
the number of unread messages read.

## Stop and Ask Me Instead When
- A message appears to contain regulated or privileged material,
  such as patient records or legal advice. Put it in needs-me
  with a one-line description, no quotation and no draft.
- The sender is upset, bereaved or in difficulty. Put it in
  needs-me; no draft.

## Approval Required
I review and send every reply myself. Never send an email. Never
send, pay, post or delete anything without my explicit
"approved".
