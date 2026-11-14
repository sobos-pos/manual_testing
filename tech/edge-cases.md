# Edge cases checklist

Try each on the till, the waiter app, the dashboard and the guest pages where it applies.

## Doing things twice, or half-way

| ID | Check | Pass when |
|---|---|---|
| EC-01 | Double-tap every "save", "send", "pay", "settle", "charge", "accept" and "close" button | Only one action happens. One order, one bill, one payment, one drawer movement. |
| EC-02 | Refresh, or kill the app, in the middle of every multi-step flow (order, pay, split, credit note, invite, onboarding, import) | No duplicates and no half-saved records. The user can continue or restart cleanly. |
| EC-03 | A slow network (browser developer tools → "Slow 3G"; a weak Wi-Fi spot for the phones) | Loading states show. Write buttons wait. There is no way to submit twice. A request with an unknown result shows "checking" and resolves to one outcome. |
| EC-04 | Browser Back after saving or paying | No re-submission. The page shows the current state. |
| EC-05 | Session expiry while a form is half-filled | The user is told. The input is not lost silently. |

## Two people at once

| ID | Check | Pass when |
|---|---|---|
| EC-06 | The cashier on the till and a waiter on the phone settle the same bill at the same moment | It is paid once. The other gets a clear message that it is already settled, and their app does not keep retrying. |
| EC-07 | Two waiters add different dishes to the same table at the same moment | Both dishes are on the table once each. |
| EC-08 | Two waiters open the same free table at the same moment | One session, not two. |
| EC-09 | The same dish or setting open in two dashboard tabs, edited and saved in both | The second save is warned about the newer version, or wins cleanly. No silent mix of the two. |
| EC-10 | The owner marks a dish sold out, or changes its price, while a waiter and a guest have it in a cart | Sold out: neither can send it; both are told. Price: the new price shows clearly before the order is sent. |
| EC-11 | A waiter moves a table while the cashier is making its bill | One of them wins cleanly. The bill is never left pointing at an empty table. |
| EC-12 | Two guests on one table place orders at the same moment | Both rounds reach the waiter, once each. |

## Odd input

| ID | Check | Pass when |
|---|---|---|
| EC-13 | Text fields: empty, spaces only, 500 characters, emoji, `<b>bold</b>`, quotes and apostrophes, Hindi or Telugu | Clear validation. Text is shown as typed, never run as code, and looks the same on screen, on the kitchen display, on paper and in exports. |
| EC-14 | Phone numbers: 9 digits, 11 digits, starting with 0 or +91, letters | Only a valid Indian mobile number is accepted, and it is stored one way however it was typed. |
| EC-15 | Numbers and money: 0, negative, decimals, very large, commas | Clear validation. No wrong maths. A dish price above ₹1,00,000 is refused. |
| EC-16 | Dates: past dates, far-future dates, 29 February, the last day of the financial year (31 March) and the first (1 April) | Handled sensibly, in Indian time. Bill numbers start a new series for the new financial year. |
| EC-17 | Party size for a booking: 0, 1, 12, 13, 100 | 1 to 12 accepted. Others refused clearly. |

## Empty, large and in use

| ID | Check | Pass when |
|---|---|---|
| EC-18 | A brand-new outlet with no menu, no tables, no staff, no sales | Helpful empty messages on every page, the till and the waiter app. No errors or blank screens. |
| EC-19 | A menu of 500 dishes, 100 tables, 1,000 bills in a day (load the seeded history) | Pages load in a few seconds. Search and filters still work. The till and waiter app stay quick. |
| EC-20 | Delete things that are in use: a category with dishes, a dish on an open order, a table with an open order, a staff member with open tables, a role people hold, a supplier with unpaid bills | Blocked with a clear reason, or handled safely. Old bills still show the deleted dish's name and price. |
| EC-21 | Deactivate an outlet (use the **second** outlet, never Main Outlet) while it has an open table and an unpaid bill | Refused, with the reasons in plain words (e.g. "2 tables open, 1 bill not settled"). After they are cleared it deactivates, and can be reactivated. |
| EC-22 | A dish's kitchen station is deleted or renamed | Its tickets still reach a display or a printer. |

## Imports and exports

| ID | Check | Pass when |
|---|---|---|
| EC-23 | Import a menu sheet into the **second** outlet: new dishes, and dishes whose names already exist | The preview shows new ones as new and existing ones as updates. After confirming, there are no duplicates. A sheet with a bad row says which row and why, and imports nothing half-way. |
| EC-24 | Import customers and opening stock | Counts in the preview match the sheet. Phone numbers are stored one way. |
| EC-25 | Export bills and a report for a month, with dish names containing commas, quotes and Hindi | The file opens correctly in Excel. Numbers match the screen. |
| EC-26 | Export a very large date range | It completes, or says clearly that it will be ready later. It never hangs the page. |

## Messages and alerts

| ID | Check | Pass when |
|---|---|---|
| EC-27 | Every notification (bell, waiter app, SMS) | Arrives once, with the right content, and opens the right place. |
| EC-28 | Low stock, a guest order waiting, a printer down, a till offline | The right person is told, once, and the alert clears when the cause is fixed. |
| EC-29 | Every error message you met during the round | Says what happened and what to do next, in plain words, with a short reference code. Never a raw code name alone. |
