# Sync and reconciliation checklist

The till sells on its own and sends everything to the cloud. The dashboard, the reports and the owner's phone all read the cloud. This checklist proves the two hold the same records.

Run it **after every testing day**, and again after each outage in `till-and-offline.md`. The best day to run it is the full-day script (`../scripts/7-full-day.md`), because its totals are known in advance.

**Setup:** the till's Today's bills and Cash drawer screens on one side, the dashboard (Orders & Billing, Analytics, Node & Devices) on the other.

## The till and the dashboard agree

| ID | Check | Pass when |
|---|---|---|
| SY-01 | Number of paid bills today | The same on the till and in Dashboard → Bills. |
| SY-02 | Every bill number on the till | Each appears in the dashboard exactly once. No number appears twice anywhere. |
| SY-03 | Open five bills on both sides, including one with a discount, one with the service charge waived and one split payment | Dishes, quantities, prices, discount, charges, each tax line, round off and total are identical to the paisa. Each payment has the same method and amount. |
| SY-04 | Totals by payment method | Cash, Card and UPI on the till's X or Z report equal the dashboard's payment-method report for the same business day. |
| SY-05 | Voids, walk-outs and credit notes | Each one made on the till is in the dashboard with the same amount, reason and people. |
| SY-06 | The drawer | Dashboard → Shifts shows the same float, pay ins, pay outs, safe drops, expected cash, counted cash and difference as the till, with who approved a difference above ₹500. |
| SY-07 | Orders and kitchen tickets | Each order's dishes and each cancelled dish match. A guest order declined on the till is declined in the dashboard. |
| SY-08 | Customer names | A takeaway's customer name and phone, and a guest added at payment, show on the dashboard's order and bill. |
| SY-09 | Card slip number and approval code | Shown on the dashboard's bill for that payment. |
| SY-10 | Tables | A table moved, joined or closed on the till shows the same in Dashboard → Tables within a few seconds. |
| SY-11 | Sold out | A dish marked sold out on the till or the waiter app shows as sold out in the dashboard and on the guest menu, and comes back everywhere when restored. |
| SY-12 | Stock | Selling 3 `TEST Lemon Soda` on the till lowers `TEST Lemons` by 6 in the dashboard. Cancelling one before it is sent to the kitchen moves no stock. |
| SY-13 | Attendance | Clock-ins and clock-outs made on the waiter app or the till are in the dashboard with the right times. |

## The dashboard reaches the till

| ID | Check | Pass when |
|---|---|---|
| SY-14 | Change a `TEST` dish's price in the dashboard | The till and both waiter phones show the new price within a minute or two, without restarting. |
| SY-15 | Add a `TEST` table and a `TEST` cancel reason | Both appear on the till and the waiter app. |
| SY-16 | Change a setting the till uses (e.g. "Lock the till after") | The till follows. Change it back. |
| SY-17 | Set a new till PIN for a `TEST` staff member | The new PIN works on the till; the old one does not. |

## Nothing is lost or doubled

| ID | Check | Pass when |
|---|---|---|
| SY-18 | Cut the internet in the middle of a busy minute (bills being settled), restore it after 5 minutes | Every bill made during the cut arrives once. |
| SY-19 | Kill the till app while it is sending the backlog, then restart it | It carries on from where it stopped. No bill, payment or drawer movement arrives twice. |
| SY-20 | Dashboard → Node & Devices → Conflicts and Alerts, after each outage | Empty, or each entry is explained in plain words. Any sale the cloud refused is listed there, not silently dropped. |
| SY-21 | The till's lock screen after reconnect | It says all sales are sent only when that is true. Compare with SY-01. |
| SY-22 | Try to edit an order or bill made on the till from the dashboard | Refused: the till owns it. The dashboard can watch it but not change it. |

## The day adds up

| ID | Check | Pass when |
|---|---|---|
| SY-23 | Z report against the bills | Sales on the Z equal the sum of the day's paid bills. Tax on the Z equals the sum of the bills' tax lines. |
| SY-24 | Dashboard sales summary against the Z | Net sales, tax, charges, discounts, round off and total collected match for the same business day. |
| SY-25 | The full-day script's final table | The Z report, the dashboard and the testers' cash sheets all show ₹10,483.00 collected (₹1,630.00 cash, ₹3,267.33 UPI, ₹5,585.67 card) and ₹3,514.50 in the drawer. |
