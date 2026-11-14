# Tech team checklists

These cover what non-tech testers can't: the real printer, the till's installation and offline behaviour, sync with the cloud, exact money rules, security, and the platform console. Many need setup (printers, a till PC, a way to cut the internet, a second outlet).

Non-tech testers use the till's screens in their own scripts. **The printer, the cash drawer hardware and everything on this page are yours.**

## How to use them

- Each line has an ID (e.g. `PR-07`). Report bugs the same way as everyone else: screenshot plus one line to your AI, with the ID as the step.
- Add **tech details** to every bug: the failing request's address and status code, the response message, the reference code on the error, and for the till the lines from its log around that time. **Never include tokens, cookies, keys or PINs.**
- Test by hand in the app. These checklists are for people, not for automation.
- Use the standard test restaurant (`../SETUP.md`). Where a check needs a setting changed, change it, run the check, and **change it back** before non-tech testers continue.
- Expected money figures come from [the answer sheet](../TEST-RESTAURANT.md). Any difference, even one paisa on a tax line, is a bug.

## Checklists

| File | IDs | Area |
|---|---|---|
| [printer.md](printer.md) | PR | Bills, kitchen tickets, reports, printer failures, cash drawer |
| [till-and-offline.md](till-and-offline.md) | TL, OF, AL, TM, CL | Installing the till, PINs, internet down, alerts, dates |
| [sync-and-reconciliation.md](sync-and-reconciliation.md) | SY | The till and the cloud holding the same records |
| [money-and-tax.md](money-and-tax.md) | MT | Rounding, GST, charges, discounts, splits, credit notes, bill numbers, day end |
| [kitchen-screen.md](kitchen-screen.md) | KD | Kitchen display behaviour and its paper fallback |
| [guest-ordering-security.md](guest-ordering-security.md) | GS | Pairing codes, table PINs, who can order on which table, guest payment |
| [payments-and-messages.md](payments-and-messages.md) | PM | Razorpay QR and refunds, OTP and other messages, photos |
| [roles-and-security.md](roles-and-security.md) | RS | Who can see and do what, sign-in, data isolation |
| [edge-cases.md](edge-cases.md) | EC | Double clicks, refreshes, two users at once, odd inputs, large data, imports |
| [devices-and-browsers.md](devices-and-browsers.md) | DB | Browsers, screen sizes, phones, keyboard |
| [platform-console.md](platform-console.md) | PC | Platform admin: tenants, plans, flags, templates, support access |

## Your daily part

1. Before testers start: the round checklist in `../SETUP.md` section 6, including the answer check.
2. Run your checklist items.
3. Re-check the non-tech bugs you can reproduce. Add tech details to the bug file.
4. Tech lead: update and confirm `../TRIAGE.md` (see `../HOW-IT-WORKS.md`).
5. When a fix is deployed, re-check it and the features next to it.

## Finding which part is at fault

| Where the tester was | First look |
|---|---|
| Dashboard, guest menu, booking page, console | Browser developer tools (F12) → Network. A wrong or failed response is the backend; a right response shown wrongly is the web app. |
| Till, Billing screens | The till's own log (This device → logs) and its local server. The till prices and numbers bills itself, so a wrong total on the till is the till, not the backend. |
| Waiter app | The waiter app talks to the till. Check the till's log for the request first, then the app. |
| Till and dashboard disagree | Sync. Start with `sync-and-reconciliation.md` and Node & Devices → Conflicts. |
| Paper wrong, screen right | Printer or print template. |
