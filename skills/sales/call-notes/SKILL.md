---
name: call-notes
description: Logs call notes to the CRM and creates follow-ups
version: 1.5.0
metadata:
  hermes:
    tags: [sales, crm, playbook-10]
    category: sales
---

# Call notes into the system, in ninety seconds

## When to Use
When I send notes or a voice note right after a call and say
"log it".

## Procedure
1. Check the person against my client list. My client list is the
   customers and contacts named in Sales/orders.csv,
   Sales/pipeline.md and Sales/renewals.md (change these to
   wherever your own client list lives). If the PERSON's name
   is not written in any of them (even if the company is), do
   not stop and do not create a record: carry on with steps 2 to
   4 and end the echo with this line, word for word: "Not in
   client list: add this person to the client record? yes or no".
2. Extract interest, objection, next action, date and
   stakeholders (other people named in the notes who matter to
   this deal). Record the objection close to verbatim. The date
   is the next-action date, not the date of the call.
3. Take out anything about health, family, legal, HR or other
   personal matters. These never go to the CRM, and you must not
   repeat them anywhere in your reply, not even to say what they
   were. In their place write this line, word for word: "Left
   out: one personal matter (not repeated here)." If there are
   several, write "several personal matters".
4. ECHO BACK to me, in this order: interest, objection, next
   action, date, stakeholders. If a price or terms were agreed,
   write them as "to confirm in writing" and add the line:
   "Reminder for you: confirm the price in writing yourself."
5. STOP. Write nothing to the CRM and create no task in this
   reply. Wait for me to answer "approved" or send corrections.
6. After I say "approved": write the fields to the CRM (or, if I
   have none, to the client's entry in Sales/pipeline.md), create the follow-up task for any deadline
   mentioned, and confirm in one line.

## Pitfalls
- Voice notes mistranscribe company and people's names. Match
  against the client list and ask when unsure rather than
  creating a duplicate record.
- A stated deadline ("pricing by Friday") is a commitment.
  Create the task once I approve; never just note the sentence.
- Do not summarise away the objection. It is the most valuable
  field.

## Verification
Your first reply contains the echo of the five fields and
nothing has been saved. It contains no personal detail, only
the "Left out" line. After "approved", the CRM entry matches the
echo.

## When You Find These
- The notes cover health, legal, HR or personal matters. Keep
  those parts out of the CRM and tell me what you left out,
  using the line in step 3 and nothing more.
- A price or terms were agreed on the call. Record them as "to
  confirm in writing" and remind me to confirm them myself.
- You cannot match the person to the client list. Add the line
  from step 1.

## Approval Required
Echo the key fields back to me and wait for "approved" before
saving anything to the CRM or creating any task. Never send,
pay, post or delete anything without my explicit "approved".
