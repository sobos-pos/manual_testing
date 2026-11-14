# How this works (for the manager and tech lead)

## The flow

```
Tech lead sets up the test restaurant and names the round          (SETUP.md)
        ↓
Testers follow scripts by hand on the real app
        ↓  screenshot + one line
Their own AI checks it against the answer sheet and known limits,
writes bugs/<name>/BUG-<name>-NNN.md, keeps progress and the cash sheet, and pushes
        ↓  every day
Tech lead asks an AI to "update triage" → TRIAGE.md gets new rows
        ↓
Tech team confirms each row: area, likely fault, priority, effort, owner
        ↓
Developer fixes → tech lead marks it "Fixed" → same tester re-checks → "Retest passed"
        ↓
GO-LIVE.md is signed when its conditions are met
```

## Who does what

| | Non-tech team | Tech team |
|---|---|---|
| Tests | Scripts 1 to 7: the owner's dashboard, the till, the waiter app, the kitchen display, customer ordering, the manager's work, and a full day of service | `tech/` checklists: the real printer and cash drawer, installing the till, offline, sync, exact money rules, security, devices, the platform console |
| The till | Uses its screens as a cashier, manager and cook | Installs it, connects the printer and drawer, and tests the hardware |
| Reports | Screenshot and one line to their AI | Same, plus request and log details |
| Triage | — | Confirms every row in `TRIAGE.md` daily |
| Re-check | Re-tests their own fixed bugs | Re-tests tech bugs; checks fixes didn't break nearby things |

The non-tech team never decides where the fault is, or the priority. They only describe what they saw.

## The files

| File | For | What it is |
|---|---|---|
| `README.md` | Testers | Start here |
| `TEST-RESTAURANT.md` | Everyone | The standard restaurant, its prices, and the right total for every standard order |
| `KNOWN-LIMITS.md` | Everyone | What is not in this release, what is intended, open questions |
| `scripts/` | Non-tech testers | Seven role scripts |
| `tech/` | Tech team | Eleven checklists |
| `SETUP.md` | Tech lead | Building the test restaurant, the settings, the round record, the pre-round check |
| `AGENTS.md` | The testers' AI tools | How to write reports, progress and cash sheets |
| `TRIAGE.md` | Tech team | Every bug, its owner and status |
| `COVERAGE.md` | Manager, tech lead | Which script or checklist tests which part of the product |
| `GO-LIVE.md` | Owner, manager, tech lead | The conditions for going live, and the sign-off |

## Rounds

Name each round by its start date, e.g. `R1 2026-11-17`. Testers tell their AI the round name, so every result is recorded against it.

| Round | What runs | Purpose |
|---|---|---|
| **R1** | Every tester runs their own script (1 to 6). Tech team runs every checklist. | Find the bugs. |
| **R2** | Retest every Fixed bug. Re-run any script section that had a P0 or P1. Then the whole team runs script 7 (a full day). | Prove the fixes, and prove a day adds up. |
| **R3** (final) | Script 7 again on the release build, plus `tech/sync-and-reconciliation.md`, `tech/money-and-tax.md` and `tech/printer.md`. | The build that goes live is the build that passed. |

Add rounds if R3 finds a P0 or P1. A new build always means a new round name.

## Before the first round (tech team)

Everything is in `SETUP.md`. In short:

- Build the standard test restaurant and set the listed settings.
- One login per tester, each with their own till PIN. Send links and logins privately.
- Invite each tester's GitHub account with **write** access, so their AI can push.
- Till PC with printers and drawer, kitchen display, two waiter phones, table QR stickers.
- Decide how testers pay: play money for cash, Razorpay in test mode for UPI.
- **Trial run:** one tester runs one script section for 15 minutes. Fix whatever confused them, then start everyone.

## Daily routine (about 30 minutes)

1. Before testers start: the pre-round check in `SETUP.md` section 6. The answer check (order A is ₹785, T1 is ₹483) takes two minutes and saves a day of false reports.
2. After testers finish: open this repo in an AI tool: *"Read AGENTS.md. I'm the tech lead. Update triage."*
3. Go through new rows in `TRIAGE.md`. For each, open the bug and reproduce if unsure. Correct the columns, set **Owner**, and set **Confirmed = Yes**.
4. Merge duplicates: set the copy's Status to `Duplicate of BUG-…`.
5. Look at "Script progress this round": chase steps that are **Blocked** (they are yours to unblock) and steps not run.
6. Push. Developers pick up the P0 rows first, then P1.
7. When a fix is deployed: *"Mark BUG-… fixed in <build>."* The tester's AI then lists it when they ask what to retest.

## Deciding where the fault is

`tech/README.md` has the table. The short version: the till prices and numbers its own bills, and the waiter app asks the till, so a wrong total there is the **till**. A wrong or missing record in the dashboard after a sale is **sync**. A server error on the dashboard, guest pages or console is the **backend**. Right data shown wrongly is the **screen**. Right screen, wrong paper is the **printer**.

## Definitions

| Priority | Meaning | Fix when |
|---|---|---|
| P0 | Money differs from the answer sheet; a bill, order or payment lost or doubled; a bill number repeated; can't sign in, order, bill or pay; an offline sale missing from the dashboard; data seen across restaurants, outlets or tables; a manager-only action done without a manager | Before going live |
| P1 | Main feature broken, workaround exists | Before going live |
| P2 | Minor feature broken, or confusing | After going live, unless the owner says otherwise |
| P3 | Cosmetic issues, wording | When convenient |

| Effort | Meaning |
|---|---|
| XS | under 1 hour |
| S | up to half a day |
| M | about 1 day |
| L | 2–3 days |
| XL | needs a design or owner decision first |

| Status | Meaning |
|---|---|
| New | not looked at yet |
| Confirmed | tech team reproduced it |
| In progress | developer working on it |
| Fixed | fix deployed, waiting for re-check |
| Retest passed | tester confirmed the fix |
| Retest failed | still broken, goes back to In progress |
| Not a bug | works as designed (explain in the bug file, and add it to `KNOWN-LIMITS.md` if others will hit it) |
| Needs owner decision | the product rule itself is in question |
| Duplicate of BUG-… | same as another bug |

Step results in a tester's `progress.md`: Pass, Fail, Known (a listed limit or open question), Not there, Blocked, Skipped.

## Release rule

`GO-LIVE.md` holds the full conditions and the sign-off. The core of it: no open P0 or P1, every P0 has **Retest passed**, and a full day of service adds up to the rupee on the release build.

## Keeping the kit true

- **When the product changes,** update the script step and `KNOWN-LIMITS.md` in the same week. A script that expects old behaviour produces false bugs.
- **When a tester reports "the script is wrong",** it arrives as a bug with App = "Test script". Fix the script, or mark it Not a bug.
- **The answer sheet** in `TEST-RESTAURANT.md` was worked out with the backend's own pricing rules (`backend_api/backend/src/apps/operations/orders/services/pricing.py`): GST rounded half up on each component of each line, the service charge after discounts, round off to the nearest rupee. If a price, a tax rate, the service charge or the packaging charge changes, work every row out again before the next round.
- **An open question that gets decided** moves out of `KNOWN-LIMITS.md`'s open questions, and the steps that mention it are updated.
