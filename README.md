# SoBoss manual testing: start here

You test the SoBoss restaurant system by hand, the way a real owner, manager, cashier, waiter, cook or customer would use it. When something is wrong, your AI assistant writes the bug report for you.

This is the last round of testing before real restaurants use the system. Be strict: if money is off by one rupee, report it.

## What you get from us

- **Links and logins**, sent to you privately. Never put them in this folder.
- **An invite to this GitHub repo.** Accept it from your email.
- **Your script**, in the `scripts/` folder.

## What you need

An AI tool that can open a folder on your computer, using your own account. Any of these works: Codex, Cursor, Claude Code, Gemini CLI, or GitHub Copilot in VS Code. A normal chat website cannot save files, so it won't work here.

## First day (15 minutes, the tech team helps)

1. Download this repo to your computer. Your AI can do it if you give it the repo link: "clone this repo".
2. Open the folder in your AI tool.
3. Type: **"Read AGENTS.md. I'm a tester."**
4. Tell it your first name, your team (non-tech or tech) and the round name the tech lead gave you (e.g. `R1 2026-11-17`).
5. Read [the test restaurant](TEST-RESTAURANT.md) and [known limits](KNOWN-LIMITS.md). Keep the test restaurant page open while you test: it has the prices and the right total for every standard order.

## Every testing day

1. Open your script in `scripts/` and do the steps one by one in the real app.
2. **Something wrong?**
   - Take a screenshot. Draw a red circle on the problem if you can.
   - Put the screenshot file into `bugs/<your-name>/inbox/`.
   - Tell your AI in one line, e.g. *"Step C-31, Order A on table 4, bill says 790 not 785."*
   - Answer its one or two questions. It saves and uploads the report.
3. **Steps worked?** Tell your AI, e.g. *"C-01 to C-30 passed."*
4. **Option not on your screen?** *"C-21 not there."*
5. **Can't do a step because something isn't set up?** (no printer, no teammate, login doesn't work) *"C-57 blocked, no teammate."*
6. **Took cash, gave change, put cash in or out of the drawer?** Tell your AI, e.g. *"Cash: Order A, 785, given 800, change 15."* It keeps your cash sheet, so the drawer can be checked at the end.

## Which script is yours

| Script | You are | You use | Time |
|---|---|---|---|
| [1: Owner](scripts/1-owner-dashboard.md) | The owner, setting up and watching the business | Dashboard on a laptop | 3 hours, over two days |
| [2: Cashier at the till](scripts/2-cashier-till.md) | The cashier at the counter | The till | 3 hours |
| [3: Waiter](scripts/3-waiter-app.md) | A waiter on the floor | Waiter app on an Android phone | 2.5 hours |
| [4: Kitchen](scripts/4-kitchen-screen.md) | A cook | The kitchen display | 1 hour |
| [5: Customer](scripts/5-customer-qr-ordering.md) | A guest at a table | Your own phone | 1.5 hours |
| [6: Manager](scripts/6-manager.md) | The outlet manager | The till and the dashboard | 2 hours |
| [7: A full day of service](scripts/7-full-day.md) | The whole team together | Everything | 3 hours |
| [Tech checklists](tech/README.md) | Tech team | Printer, offline, money, security | — |

Scripts 3, 4 and 5 need a teammate for some steps; each step says so. Run script 7 last, after everyone has finished their own.

## What counts as a bug

Report anything that is:

- **Wrong money:** a price, total, tax, change or drawer figure that does not match the test restaurant page. Even ₹1.
- **Broken:** an error, a button that does nothing, a crash.
- **Wrong:** a name, table, time, date or status that doesn't match what really happened.
- **Lost or doubled:** an order, bill or payment that disappears or appears twice.
- **Slow:** a tap at the till or in the waiter app that takes more than about 2 seconds, or a page that takes more than about 5 seconds.
- **Confusing:** you didn't know what to do next, or a message didn't tell you what went wrong.
- **Looks bad:** cut-off text, overlapping parts, spelling mistakes.

When in doubt, report it. A wrong report costs nothing.

## Always tell your AI these

- The **step number**.
- The **bill number, table or order** it happened on, and the **amount you expected and the amount you saw**.
- Whether the **internet was on or off** at the time.
- Any **reference code** shown in the error message.

## Screenshots

- **Windows:** `Win + Shift + S`, then select the area. It saves to `Pictures\Screenshots`. Drag the file into your `inbox` folder.
- **Phone:** take a screenshot, then send it to your computer (WhatsApp Web, email or Drive) and save it into `inbox`.
- **Recording:** a short screen recording helps when the problem only happens while moving. Keep it under 20 MB, or share a link.

## Rules

- **Test by hand.** Never ask your AI to click, open or test the app for you. It only writes reports.
- **Don't change the standard menu.** Never rename, reprice or delete a dish, table or setting from the test restaurant page. Anything you create starts with `TEST` (e.g. `TEST Lemon Soda`).
- **Pay only the way the tech lead tells you.** Never use real money unless they say so.
- **Don't capture secrets.** Never screenshot or type passwords, OTPs or PINs into a report.
- **One person, one login.** Never share a login or a till PIN with another tester.
- **Ask for help.** If you're stuck because of setup, tell the tech lead, and tell your AI the step is blocked.

## For the manager and tech lead

[How this works](HOW-IT-WORKS.md) · [Setup](SETUP.md) · [Bug triage](TRIAGE.md) · [What is tested where](COVERAGE.md) · [Go-live sign-off](GO-LIVE.md)
