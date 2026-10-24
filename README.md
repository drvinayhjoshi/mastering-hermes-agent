# Mastering Hermes Agent: Companion Repository

The downloadable companion to *Mastering Hermes Agent: 25 Practical Automations for Small Businesses* by Dr. Vinay Joshi.

Everything here is plain text. Download rather than retype: it saves time, and it avoids the one typo that breaks a configuration file.

**Tested against Hermes Agent v0.22.5 on October 24, 2026.** Eleven skills were rewritten after a first test and then tested three times; the other twenty-one were tested once and are unchanged. Each skill's status is in its INDEX file and in Appendix G.7 of the book. The skills printed in the book are identical to the files here. If a command no longer works, check [ERRATA.md](ERRATA.md) first.

## What's here

| Folder | What it holds | Book reference |
| --- | --- | --- |
| [`skills/`](skills/INDEX.md) | All 25 playbook skills, one `SKILL.md` each, in five folders that match Part Four | Part Four |
| [`bonus-skills/`](bonus-skills/INDEX.md) | Seven more: subscription audit, competitor watch, ad guardrail, content gaps, month-end close, recruitment shortlist, offboarding | Part Four, Bonus Skills |
| [`templates/`](templates/) | Blank skill template, the first-30-days worksheet, and starter files for the bank balance, obligations, renewals, suppliers, project status rules and the mentions watchlist | Chapters 4 and 7; Playbooks 3, 4, 12, 15, 16, 22, 24 |
| [`config-examples/`](config-examples/) | Delegation, MCP servers, approval and deny rules, shell setup, and a messaging `.env` example for every channel in 5.4 | Chapters 5, 6, 9, Appendix A |
| [`docker/`](docker/) | A `docker-compose.yml` for the official Hermes image | Chapter 10 |
| [`ERRATA.md`](ERRATA.md) | Corrections and changes since publication | Chapter 11 |

## Installing a skill

1. Copy the skill's folder into your skills library, keeping the category folder. For example, for the invoice chase:

   ```bash
   mkdir -p ~/.hermes/skills/finance
   cp -r skills/finance/invoice-chase ~/.hermes/skills/finance/
   ```

2. Open the `SKILL.md` and **change every folder path** (`~/Business/...`) to where your files actually live.
3. Check Hermes can see it: `hermes skills list`.
4. Run it by hand first, in a chat: `/invoice-chase`. Check the output. Only schedule it once you trust it; the suggested schedules are in [skills/INDEX.md](skills/INDEX.md).

Each skill also has a **Stop and Ask Me Instead When** section, written as instructions to the agent, so it knows when to hand the job back to you. Inside a skill, "I" and "me" are you, the owner; "you" is Hermes.

Every skill drafts or reports to you. None of them sends, pays, posts or deletes anything on its own, and each has an **Approval Required** section saying where it stops. Please keep it that way.

**Installing one skill straight from GitHub.** Open the skill's `SKILL.md` here, click **Raw**, copy the address, and run `hermes skills install <address> --category finance` (use the skill's own category). Then do steps 2 to 4 above.

Appendix G of the book walks through all of this in more detail.

## Using the configuration examples

The `.yaml` files in `config-examples/` are fragments to **merge** into your `~/.hermes/config.yaml`, not replacements for it. Open your config with `hermes config edit`, paste in the section you need, and keep the indentation exactly as shown. After adding MCP servers, type `/reload-mcp` in a chat.

## Scheduling reminder

Scheduled jobs only run while the Hermes gateway is running. Set it up once with `hermes gateway install`. By default a job's result is saved on your machine; add `--deliver telegram` (or your platform) to receive it on your phone.

## Reporting a correction

Hermes changes quickly. If something in the book or this repository no longer works, please open an issue with:

- the page or section of the book
- your operating system and `hermes --version`
- the command you ran and the complete error message

## Disclaimer

This is an independent, unofficial companion to an independent book. It is not affiliated with or endorsed by Nous Research. The skills are examples to adapt; you remain responsible for what your agent does with your data. Nothing here is legal, tax, accounting or financial advice.

`messaging.env.example` is different: it shows the lines `hermes gateway setup` writes to `~/.hermes/.env` for each messaging channel in Chapter 5, so you can check what was stored. Never commit your real `.env` anywhere.
