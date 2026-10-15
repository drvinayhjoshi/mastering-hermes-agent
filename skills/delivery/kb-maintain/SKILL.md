---
name: kb-maintain
description: Turns repeated support answers into a knowledge base
version: 1.2.0
metadata:
  hermes:
    tags: [delivery, knowledge-base, playbook-18]
    category: delivery
---

# A knowledge base that maintains itself

## When to Use
When I ask to refresh or update the knowledge base.

## Procedure
1. Read the replies in ~/Business/Support/sent/.
2. Group them by underlying question.
3. For each question answered more than three times, write one
   canonical answer.
4. Update ~/Business/Support/kb.md, grouped by theme, leaving
   entries marked [reviewed] untouched.
5. Report where past answers were inconsistent.

## Pitfalls
- Never overwrite an answer I have edited. Edited entries are
  marked [reviewed]; update around them and tell me what you
  would have changed.
- Prices, turnaround times and policies change. Any answer
  containing a number gets a "verify" flag for me.
- Inconsistent past answers are a finding, not a problem to
  average away. Report both versions.

## Verification
State how many questions were clustered, how many met the
three-time threshold, and how many entries were left untouched
because they were marked reviewed.

## Stop and Ask Me Instead When
- The answer is a policy or legal statement: refunds,
  guarantees, how we handle data. Propose wording marked [FOR
  REVIEW]; never present it as settled.
- Past answers from different people disagree. Report both
  versions and ask me which is right; do not merge them.

## Approval Required
I review kb.md monthly. Never overwrite an entry marked
[reviewed]. Never send, pay, post or delete anything without my
explicit "approved".
