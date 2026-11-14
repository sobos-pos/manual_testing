# SoBoss manual testing — start here

You test the SoBoss restaurant system by hand, like a real owner, cashier, waiter or customer would. When something is wrong, your AI assistant writes the bug report for you.

## What you get from us

- **Links and logins**, sent to you privately. Never put them in this folder.
- **An invite to this GitHub repo.** Accept it from your email.
- **Your script**, in the `scripts/` folder.

## What you need

An AI tool that can open a folder on your computer, using your own account. Any of these works: Codex, Cursor, Claude Code, Gemini CLI, or GitHub Copilot in VS Code. A normal chat website cannot save files, so it won't work here.

## First day (10 minutes, the tech team helps)

1. Download this repo to your computer. Your AI can do it if you give it the repo link: "clone this repo".
2. Open the folder in your AI tool.
3. Type: **"Read AGENTS.md. I'm a tester."**
4. Tell it your first name and team (non-tech or tech) when it asks.

Use Claude Code? Start **every** new chat with "Read AGENTS.md first."

## Every testing day

1. Open your script in `scripts/` and do the steps one by one in the real app.
2. **Something wrong?**
   - Take a screenshot. Draw a red circle on the problem if you can.
   - Put the screenshot file into `bugs/<your-name>/inbox/`.
   - Tell your AI in one line, e.g. *"Step C-08, clicked Pay, it kept loading for a minute, then said Something went wrong."*
   - Answer its one or two questions. It saves and uploads the report.
3. **Steps worked?** At the end tell your AI, e.g. *"Finished cashier script, everything else passed."*
4. **Option not on your screen?** Tell your AI: *"C-09 not there."*

## What counts as a bug

Report anything that is:

- **Broken:** an error, a button that does nothing, a crash.
- **Wrong:** price, total, tax, date or name doesn't match.
- **Slow:** a page or action takes more than about 5 seconds.
- **Confusing:** you didn't know what to do next.
- **Looks bad:** cut-off text, overlapping parts, spelling mistakes.

When in doubt, report it. A wrong report costs nothing.

## Screenshots

- **Windows:** `Win + Shift + S`, then select the area. It saves to `Pictures\Screenshots`. Drag the file into your `inbox` folder.
- **Phone:** take a screenshot, then send it to your computer (WhatsApp Web, email or Drive) and save it into `inbox`.
- **Recording:** a short screen recording helps when the problem only happens while moving. Keep it under 20 MB, or share a link.

## Rules

- **Test by hand.** Never ask your AI to click, open or test the app for you. It only writes reports.
- **Use test data.** Start names with `TEST` (e.g. `TEST Lemon Soda`). Pay only the way the tech team tells you.
- **Don't capture secrets.** Never screenshot or type passwords, OTPs or PINs into a report.
- **Ask for help.** If you're stuck because of setup (can't sign in, link doesn't open), tell the tech lead. Report it as a bug too.

## Scripts

| Script | Who |
|---|---|
| [1 — Owner dashboard](scripts/1-owner-dashboard.md) | Non-tech |
| [2 — Cashier POS (web)](scripts/2-cashier-pos.md) | Non-tech |
| [3 — Waiter app](scripts/3-waiter-app.md) | Non-tech |
| [4 — Customer QR ordering and booking](scripts/4-customer-qr-ordering.md) | Non-tech |
| [5 — Together (two people)](scripts/5-together.md) | Non-tech, in pairs |
| [Tech checklists](tech/README.md) | Tech team |
