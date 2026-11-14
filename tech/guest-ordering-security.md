# Guest ordering and security checklist

Guest phones are the only part of SoBoss that anyone on the internet can reach. These checks prove that only a guest a waiter has paired, at that table, can send food to the kitchen.

**Setup:** two phones for guests (on mobile data, not the restaurant's Wi-Fi), one waiter phone, the till, printed QR stickers for tables 3 and 4. "How guests prove they are seated" is set to QR code or table PIN (`../SETUP.md`).

## Pairing

| ID | Check | Pass when |
|---|---|---|
| GS-01 | Scan a table QR without any waiter | The menu opens. No order can be placed, by the app or by repeating its requests from developer tools. |
| GS-02 | The waiter's pairing QR, used after its screen was closed for 3 minutes | Refused as expired. The guest is told to ask the waiter for a new code. |
| GS-03 | The waiter's QR refreshes while the screen is open; a guest scans the previous one within about 15 seconds of the refresh | Accepted. After that grace it is refused. |
| GS-04 | The waiter taps Rotate; a guest uses the code shown just before | Refused at once. No grace. |
| GS-05 | A photo of the pairing QR sent to a phone elsewhere, used within its 2 minutes | It can pair, but the waiter's app shows the extra device at once, and Unpair removes it. Its orders could only ever land on that table's own bill. |
| GS-06 | Pair the same phone twice (re-scan after clearing the browser's data) | It counts as one device, not two. |
| GS-07 | Pair phones until the table's device limit is reached | The next phone is refused with a clear message. The waiter can still unpair one to make room. |
| GS-08 | The waiter opens table 3. The guest scans **table 4's** sticker for the menu, then pairs with the waiter's code | The guest's orders go to table 3, the table the waiter chose. The sticker only chose the menu. |
| GS-09 | Pair while the waiter is not clocked in | The waiter cannot show a pairing code until they clock in. A manager can. |

## Table PIN

| ID | Check | Pass when |
|---|---|---|
| GS-10 | A wrong PIN | Refused, with the number of tries left. |
| GS-11 | Five wrong PINs within 10 minutes | PIN entry for that table locks for 10 minutes, with a countdown. The waiter and the manager are alerted. The QR still works. |
| GS-12 | Three lockouts on the same table | PIN entry is off until the waiter issues a new PIN. |
| GS-13 | The PIN after the waiter taps New PIN | The old PIN is refused. |
| GS-14 | More than 5 PIN tries in one minute from one phone | Further tries are refused as too many, whatever the PIN. |
| GS-15 | The table PIN in page addresses, the till's floor screen, logs and screenshots of the dashboard | It appears nowhere except the waiter's pairing screen. |
| GS-16 | "How guests prove they are seated" set to QR only (then back) | The PIN box is not offered and a PIN is refused. |

## Who can see and order what

| ID | Check | Pass when |
|---|---|---|
| GS-17 | A paired guest edits the page address to another table's code | They see that table's menu only. Never its orders, bill or guests. |
| GS-18 | After the bill is made (table is settling), a new phone tries to pair | Refused: the bill is in progress. Phones already paired can still add a dish. |
| GS-19 | After the bill is paid, a paired phone tries to order, and reloads | Refused. The page shows the visit is over. A new party at the same table sees none of the previous party's orders. |
| GS-20 | The waiter unpairs one device with a reason | That phone cannot order. The others on the table still can. |
| GS-21 | A guest's page addresses, and the links in "Invite your table" | No phone number, name or table number that could be guessed. Only random codes. |
| GS-22 | Guest order with 50 lines, a 2,000-character note, and `<b>` or emoji in the note | Accepted within sensible limits or refused clearly. The note is shown as plain text on the till, the kitchen display and paper. |
| GS-23 | Place 10 orders in 10 seconds from one phone | Slowed down or refused as too many after a few. The kitchen is not flooded: nothing fires until the waiter accepts. |
| GS-24 | "Waiter reviews guest orders" turned off (then back **on**) | A paired guest's order goes straight to the kitchen. |
| GS-25 | "Who can order from a table" set to staff only (then back) | Guests can browse but never order, paired or not. |
| GS-26 | "Guest sign-in" set to required before ordering (then back to optional) | A guest must enter their phone and a code before building a cart. The code expires after about 5 minutes and after 5 wrong tries. |

## Guests paying from their phones

Only if the pilot outlets will use it. Turn "Guests pay from their phones" on for this session, use Razorpay in test mode, and turn it **off** afterwards.

| ID | Check | Pass when |
|---|---|---|
| GS-27 | A paired guest taps Pay on **order G** | The bill is made by itself: ₹681, with the service charge and GST shown. The table goes to settling. |
| GS-28 | The guest pays the full amount | The bill is settled, the table closes, the waiter and cashier are told, and the guest sees Paid. Nothing enters the cash drawer. |
| GS-29 | Two guests each pay half | Two payments on one bill. The table closes only after the second. |
| GS-30 | The guest closes the browser straight after paying | The bill is still settled once the payment is confirmed. |
| GS-31 | Two guests pay the full amount at the same moment | The bill is settled once. The second payment is listed in Dashboard → Day end as an extra payment for a manager to refund. It is never refunded by itself and the bill is not changed. |
| GS-32 | The guest starts paying and abandons it | The bill stays open and unpaid. Staff can still take payment at the table. |
| GS-33 | Internet down at the outlet | The guest cannot pay from the phone and is told staff will take payment. |

## Takeaway by QR

Only if the outlet takes guest takeaway orders.

| ID | Check | Pass when |
|---|---|---|
| GS-34 | Order and pay online | The kitchen gets the order only after the payment is confirmed. The guest gets a collection number. |
| GS-35 | The payment times out or the guest's bank is slow | The guest sees that the payment is being confirmed. There is no retry button that could charge twice. It ends as paid (order fires) or failed (nothing was ordered, nothing charged). |
| GS-36 | The guest closes the browser after paying but before the confirmation page | The order still fires and the kitchen cooks it. |
| GS-37 | A dish goes sold out after the guest paid for it | Staff can refund that dish back to the guest's payment method. The money never stays with food that was not made. |
