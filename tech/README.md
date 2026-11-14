# Tech team checklists

These cover what non-tech testers can't: printers, the till desktop app, offline mode, money edge cases, security and the platform console. Many need setup (printers, a till PC, two tills on one network).

## How to use them

- Each line has an ID (e.g. `PR-07`). Report bugs the same way as everyone else: screenshot plus one line to your AI, with the ID as the "script step".
- Add **tech details** to every bug: console errors, the failing request's address and status code, the response message and request ID. **Never include tokens or cookies.**
- Test by hand in the app. These checklists are for people, not for automation.
- Use a test restaurant, never a live one. Use test payment modes only.

## Checklists

| File | Area |
|---|---|
| [printer.md](printer.md) | Bills, kitchen tickets (KOT), reports, printer failures |
| [till-and-offline.md](till-and-offline.md) | Till desktop app, cash drawer, internet down, two tills |
| [money-and-tax.md](money-and-tax.md) | Rounding, GST, discounts, splits, refunds, day-end |
| [roles-and-security.md](roles-and-security.md) | Who can see and do what, sign-in, data isolation |
| [edge-cases.md](edge-cases.md) | Double clicks, refreshes, two users at once, odd inputs, large data |
| [devices-and-browsers.md](devices-and-browsers.md) | Browsers, screen sizes, phones |
| [platform-console.md](platform-console.md) | Platform admin: tenants, plans, flags, tax presets |

## Your daily part

1. Run your checklist items.
2. Re-check the non-tech bugs you can reproduce. Add tech details to the bug file, or open your own linked bug.
3. Tech lead: update and confirm `TRIAGE.md` (see `HOW-IT-WORKS.md`).
4. When a fix is deployed, re-check it and nearby features.
