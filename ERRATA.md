# Errata and Updates

Corrections to *Mastering Hermes Agent* (first edition) and notes on Hermes changes since publication. Newest first.

The book was tested against **Hermes Agent v0.22.5 on October 24, 2026**. If your `hermes --version` is newer, check the entries below before assuming something is broken.

## How to use this page

1. Find your chapter or playbook below.
2. If it's not listed, run `hermes --help` or `hermes <command> --help`; the current form is usually one word away (Chapter 11).
3. Still stuck? Open an issue in this repository (see the README).

## Corrections

### October 24, 2026 · Edition checked against Hermes v0.22.5
**Changed:** the book and this repository were re-checked against Hermes Agent v0.22.5. Nine playbook skills (2, 4, 7, 9, 10, 11, 13, 21, 22) and the bonus skills content-gaps and month-end-close were rewritten and retested; see Appendix G.7.
**Also:** sessions are kept by default (`sessions.auto_prune` is false in v0.22.5); the 90-day deletion applies only if you turn pruning on. The Docker example tag is `:v0.22.5`.

<!--
Template for new entries:

### Month D, YYYY · Chapter N, section N.N (page NN)
**Book says:** `old command`
**Now:** `new command`
**Since:** Hermes vX.Y.Z
**Why:** one line
-->
