# Known limits

Read this once before you test. It saves you from reporting things that are meant to be this way, and it tells you what is not in this release.

The tech lead keeps this page up to date.

## Not in this release: don't report these as missing

| What | What you will see |
|---|---|
| Offer codes and coupons at the till or in the waiter app | Offers can be set up in the dashboard, but nothing redeems them yet |
| Loyalty points | Switched off |
| Gift cards, store credit, khata (pay later) | Not offered in the test restaurant. The till takes Cash, Card and UPI |
| Swiggy and Zomato orders | They do not arrive in the app yet |
| Guests paying from their own phone at a table | Switched off. The guest sees "Your server will take payment at the table." |
| A review or rating screen in the guest app | Not there |
| A UPI QR in the waiter app | Not there. The waiter marks UPI as paid by hand; the till shows the QR |
| Cash at the dashboard's POS page (in a browser) | Refused. Cash is taken on the till only |
| A second till taking over when the first one fails | Not part of this release. One till per outlet |
| GST e-invoice (IRN) on bills | Not in this release |
| Firing starters before mains (courses) | Not in this release |
| Barcode scanning | Not in this release |

## Meant to be this way: not a bug

| It looks wrong because | Why it is right |
|---|---|
| Bill numbers jump between tills | Each till has its own block of numbers. A number must **never repeat**; that would be a bug |
| The till locks after 5 minutes | Each person unlocks with their own PIN, so every sale has a name on it |
| A guest's phone order does not reach the kitchen at once | The table's waiter accepts it first. It then shows "Order waiting" after 90 seconds |
| The waiter's pairing code stops working | It lasts about 2 minutes. The waiter shows a fresh one |
| A paid bill cannot be changed or deleted | A manager issues a credit note instead. The original bill stays as it was |
| The cashier removes the service charge without a manager | The guest has a legal right to refuse it |
| The waiter cannot cancel a dish that went to the kitchen | It needs a manager's PIN on the waiter's phone |
| The waiter's Kitchen tab has no buttons | It is view-only. The kitchen marks food ready; the waiter marks it served |
| A cash tip cannot be recorded | Cash tips go straight to staff and never enter the till |
| Guests cannot order from their phones when the internet is down | They are told the waiter will take the order. The till and the waiter app keep working |
| The printed bill has no payment QR | It is off unless the outlet turns it on. The paid receipt never has one |
| The total changes by a paisa or two when the same dish is added in two rounds | GST is rounded on each line. **To pay** must still match the answer sheet |
| Back-office pages on the till say "This page needs the internet" | Only selling works offline. Menu, staff and reports need the internet |

## Open questions: report it once, then carry on

These are being decided. If you hit one, report it the first time and tell your AI it is a known open question.

| ID | Question | Where you meet it |
|---|---|---|
| OQ-1 | **Service charge after a discount.** The rule is that the service charge is 10% of the bill *after* the discount. Order E with 10% off should be ₹1,476. If you see ₹1,491, the service charge was not recalculated. | C-37, MT-08 |
| OQ-2 | **"Reserved" on the till's floor.** A booked table may not show as Reserved on the till or the waiter app yet, so "Seat anyway" for a reserved table may have nothing to act on. | C-25, W-09, D-12 |
| OQ-3 | **Closing the day.** The Z report is run from the till's Cash drawer screen. Whether the dashboard should also close the day is not decided. | M-27 |
