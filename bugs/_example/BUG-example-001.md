# BUG-example-001: Order A bill shows ₹790, should be ₹785

> **EXAMPLE ONLY.** This shows what a finished report looks like. It is not a real bug and is left out of triage.

| Field | Value |
|---|---|
| Reported by | example (non-tech) |
| Round | R1 2026-11-17 |
| Date and time (IST) | 2026-11-17 15:20 |
| Script step | C-31 |
| App | Till |
| Screen | Till → Billing → table 4 → bill |
| Device | Till PC, Windows 11 |
| Signed in as | cashier |
| Bill, table or order | Table 4, order A (bill not yet paid) |
| Amount expected / seen | ₹785 / ₹790 |
| Internet | On |
| How often | Every time |
| How bad | Can work around it |

## What I did
1. Seated table 4 with 2 guests.
2. Added 1 Butter Chicken, 2 Butter Naan and 1 Jeera Rice, and sent them to the kitchen.
3. Made the bill.

## What I expected
The answer sheet for order A: Subtotal ₹680.00, service charge ₹68.00, GST ₹37.40, round off −₹0.40, To pay ₹785.

## What happened
The bill showed Subtotal ₹680.00, service charge ₹68.00, GST ₹37.40, and **To pay ₹790**. There was no round off line.

## Screenshots
No screenshot (example).

## Tester's own words
> C-31 order A on table 4 bill says 790 not 785

## Possible duplicate of
None

## Tech details
(tech team only)

## Triage — AI guess, tech team confirms
| Area | Likely fault | Priority | Effort | Why |
|---|---|---|---|---|
| Till | Till | P0 | ? | The total differs from the answer sheet by ₹5; the till works out its own bills. |

## Retest
| Round | Date | Result | Note |
|---|---|---|---|
