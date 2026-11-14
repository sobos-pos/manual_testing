# BUG-example-001: Pay button keeps loading after UPI payment

> **EXAMPLE ONLY.** This shows what a finished report looks like. It is not a real bug and is left out of triage.

| Field | Value |
|---|---|
| Reported by | example (non-tech) |
| Date and time (IST) | 2026-11-14 15:20 |
| Script step | C-07 |
| App | Cashier POS (web) |
| Page or screen | POS → Takeaway → Payment |
| Device and browser | Windows laptop, Chrome |
| Signed in as | cashier |
| How often | Every time |
| How bad | Can't continue |

## What I did
1. Started a takeaway and added 2 × TEST Lemon Soda.
2. Entered the customer name "Test Ravi".
3. Chose UPI and clicked Pay.

## What I expected
The payment completes and a bill number is shown.

## What happened
The Pay button kept spinning for about a minute, then showed: "Something went wrong. Please try again."

## Screenshots
No screenshot (example).

## Tester's own words
> C-07 clicked pay with upi it kept loading for a minute then said something went wrong

## Possible duplicate of
None

## Tech details
(tech team only)

## Triage — AI guess, tech team confirms
| Platform | Layer | Priority | Effort | Why |
|---|---|---|---|---|
| Web | Backend | P0 | ? | A server error stops the cashier taking payment. |
