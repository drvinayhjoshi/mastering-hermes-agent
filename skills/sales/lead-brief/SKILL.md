---
name: lead-brief
description: Researches a new enquiry into a short brief
version: 1.11.0
metadata:
  hermes:
    tags: [sales, leads, playbook-07]
    category: sales
---

# Every inbound lead, researched before you reply

## When to Use
When an enquiry arrives, or I ask for a lead brief or who a
prospect is.

## Procedure
1. Extract the company and contact from the enquiry. Write the
   whole brief about the prospect, in the third person ("they").
   Use "we" and "our" only for my business, never for the
   prospect.
2. Check the stop rules at the end. If one applies, stop and tell
   me why; do not go on.
3. Research the company: what they do, rough size, how long
   they've been going, anything recent. Use only what the
   enquiry says and what a source you actually opened says. If
   you have no web access, or the research finds nothing
   credible, the company part of the brief is exactly these two
   lines, and then you carry on with steps 4 to 6:
   Line 1: No research possible.
   Line 2: <contact name> from <company> needs <the request>.
   The request is the part of the enquiry that says what they
   want, copied from the enquiry, with the word "our" changed to
   "their". For example, the enquiry "We need 12 menu boards for
   our new cafes" gives: "... needs 12 menu boards for their new
   cafes."
   Do not use the words our, your, we or you in these two lines,
   and do not write any word about the company that the enquiry
   does not use (for example "chain", "growing", "expanding",
   "established" or "likely").
4. Name which of our services fits, written as "Service:
   <name>". Then give a deal-size range from comparable past
   quotes only, in these parts:
   a. A past quote is a file in Quotes/sent (change this to your
      own folder of quotes we sent). Ignore rate cards, price
      lists and quotes from our suppliers: they are not past
      quotes. Never use orders, invoices or sales files for this.
   b. List the files in that folder with the computer's list
      command (ls) and count them. Each file is one past quote.
      Open every one, and name ALL of them. You may leave one
      out only if it is clearly for a different product (for
      example software); if you leave one out, say which file
      and why, on its own line. Write each quote you name in this
      form, copied exactly from the file: client (spelled as the
      file spells it), date (YYYY-MM-DD), amount with its
      currency as the file writes it.
   c. Then write the range on one line: "estimate: <currency>
      <lowest> to <currency> <highest>, from <the quotes you
      named>". The lowest and the highest are the smallest and
      the largest amount among ALL the quotes you named. This is
      an example, not your data: "estimate: INR 10,000 to INR
      30,000, from Acme Co, 2026-01-05, INR 10,000; Beta Ltd,
      2026-02-09, INR 30,000".
   d. If there are no comparable quotes, write "no comparable
      work" and give no figure. Never use a price from anywhere
      else, and never add our material or supplier costs.
5. Give one opening line, for me to read before the call. It is a
   fact from the enquiry about them, in the third person, written
   as a sentence: no greeting, no person's name, and never "let's", "we can", "we
   will", "we propose", a time or a price. It is a note for me,
   not a message to them. It must say something that line 2 does
   not, and it must not add a verb or a claim the enquiry does
   not make. Use a fact that line 2 does not already say, for
   example the web address given in the enquiry. If the enquiry
   has no such fact, write "no opening line possible".
6. The brief must be no more than 120 words, not counting source
   links or the count itself. After writing it, count the words
   with the computer's word-count command (wc -w on the text)
   and put the real count in brackets at the top. Never write a
   count you did not measure. If it is over, cut it and count
   again. Do not reply to the prospect.

A complete brief has these parts in this order, each part on its
own line: the count, the company part (step 3: line 1 and line 2
are two lines), the service and the estimate (step 4), and the
opening line (step 5). A reply that stops after the two company
lines is incomplete.

## Pitfalls
- Common company names return the wrong business. If you have
  web access, cross-check against the domain in the enquirer's
  email address before reporting anything.
- A confident brief about the wrong company is worse than none.
- A deal-size range is an estimate from our own past quotes,
  never a valuation. Do not invent a client, a quote, a product
  or a figure.
- A range that leaves out a past quote is wrong. Count the files
  in the quotes folder before you write the estimate.

## Verification
Every factual claim carries its source link, or comes from the
enquiry; for a quote, the source is the file name. Every quote
you name exists in my past-quotes files. The number of quotes
you name equals the number of files in the quotes folder, or you
have said which file you left out and why. The measured word count is 120 or fewer.

## Stop and Ask Me Instead When
- The enquiry mentions an acquisition, a legal matter, or a named
  private individual other than the person who wrote it (for
  example someone being sued or acquired). Do not search for
  those names; tell me why you stopped. The person who wrote the
  enquiry is never a reason to stop.
- The enquirer is already a client or in my contacts: their name
  is in Sales/orders.csv, pipeline.md or renewals.md. Skip the
  web research and summarise what we already know.

## Approval Required
None; the brief comes to me only. Never send, pay, post or
delete anything without my explicit "approved".
