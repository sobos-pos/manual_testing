# How this works (for the manager and tech lead)

## The flow

```
Testers follow scripts by hand on the live app
        ↓  screenshot + one line
Their own AI writes bugs/<name>/BUG-<name>-NNN.md and pushes it
        ↓  every day
Tech lead asks an AI to "update triage" → TRIAGE.md gets new rows
        ↓
Tech team confirms each row: platform, layer, priority, effort, owner
        ↓
Developer fixes → status "Fixed" → same tester re-checks → "Retest passed"
```

## Who does what

| | Non-tech team | Tech team |
|---|---|---|
| Tests | Scripts 1–5: real-life use of the dashboard, web POS, waiter app and customer QR ordering | `tech/` checklists: printer, till and offline, money and tax, roles and security, edge cases, devices, platform console |
| Reports | Screenshot and one line to their AI | Same, plus console and network details |
| Triage | — | Confirms every row in `TRIAGE.md` daily |
| Re-check | Re-tests their own fixed bugs | Re-tests tech bugs; checks fixes didn't break nearby things |

The non-tech team never decides frontend or backend, or the priority. They only describe what they saw.

## Before the first round (tech team)

- **Links and logins:** send each tester a private note with the links and a login for their role (owner, cashier, waiter, customer). Use a test restaurant, not a live one.
- **Repo access:** invite each tester's GitHub account with **write** access, so their AI can push.
- **Test data:** prepare a menu with a few items that have sizes and add-ons, a few tables with QR codes, and staff accounts for each role.
- **Payments:** decide how testers pay (test UPI or card) and tell them.
- **Waiter app:** decide how testers get it (install link or web link).
- **Trial run:** one tester runs one script for 15 minutes. Fix whatever confused them, then start everyone.

## Daily routine (about 30 minutes)

1. The tech lead opens this repo in an AI tool: *"Read AGENTS.md. I'm the tech lead. Update triage."*
2. Go through new rows in `TRIAGE.md`. For each, open the bug and reproduce if unsure. Correct the columns, set **Owner**, and set **Confirmed = Yes**.
3. Merge duplicates: set the copy's Status to `Duplicate of BUG-…`.
4. Push. Developers pick up the P0 rows first, then P1.

## How the tech team decides the layer

Open the browser's developer tools (F12) → Network tab, and repeat the step.

- **Backend:** the server's response is wrong or an error (4xx/5xx with a bad message).
- **Frontend:** the server's response is right but the screen shows it wrong, or nothing is sent at all.
- **Till app:** the problem only happens on the till desktop app, or while offline.
- **Printer:** the screen is right but the paper is wrong.
- **Setup or data:** missing or wrong test data or configuration, not a code problem.

## Definitions

| Priority | Meaning | Fix when |
|---|---|---|
| P0 | Money or tax wrong, data lost, can't sign in, can't order, bill or pay, data leak | Before the pilot |
| P1 | Main feature broken, workaround exists | Before the pilot if possible |
| P2 | Minor feature broken, or confusing | After the pilot |
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
| Not a bug | works as designed (explain in the bug file) |
| Duplicate of BUG-… | same as another bug |

## Release rule

Go live only when there are no open P0 or P1 bugs, and every P0 has **Retest passed**.

## Testing rounds

Name each round by date, e.g. `R1 2026-11-17`. When a new build is deployed, tell testers to re-run their scripts. Mark fixed bugs **Fixed** so they know what to re-check.
