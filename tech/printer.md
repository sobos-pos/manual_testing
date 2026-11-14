# Printer checklist

**Setup:** the till PC, at least one receipt printer (80 mm, plus 58 mm if supported) on USB and on the network if both are supported, a kitchen printer on a separate route if you have one, and a cash drawer. Write down the printer models, the connection type and each printer's IP address in the round record (`../SETUP.md`).

Use the standard orders from [the answer sheet](../TEST-RESTAURANT.md) so the paper can be checked against known figures.

## What prints

| ID | Check | Pass when |
|---|---|---|
| PR-01 | The bill for **order A**, printed when the bill is made (before payment) | Restaurant name, address, GSTIN, FSSAI number, table, date and time (IST), each dish with quantity and price, Subtotal ₹680.00, service charge ₹68.00, CGST and SGST shown separately and adding to ₹37.40, round off −₹0.40, total ₹785. It carries **no invoice number** and does not call itself a tax invoice. |
| PR-02 | The receipt for order A after payment | Same figures, plus the invoice number, the payment method, cash given and change. |
| PR-03 | Order A with the service charge waived | No service charge line (or shown as waived), GST ₹34.00, total ₹714. |
| PR-04 | Takeaway **T2** receipt and token slip | Packaging ₹10.00, round off +₹0.50, total ₹284, the customer's name, the pickup token. No service charge. |
| PR-05 | Kitchen ticket (KOT) for order A | Table, dishes, quantities, add-ons and notes. No prices. The ticket number matches the till's "Sent to the kitchen". A takeaway ticket shows the customer's name and token. |
| PR-06 | Kitchen ticket routing | Butter Naan prints at the Tandoor route, Butter Chicken and Jeera Rice at Main Kitchen, drinks at the Beverage Bar. A station with no printer of its own falls back to the till's printer. |
| PR-07 | Second round | Only the new dishes print, not the whole order again. |
| PR-08 | Quantity reduced, and dish cancelled, after the first ticket | A change ticket prints, or a void ticket, clearly marked. The kitchen is never left to guess. |
| PR-09 | Reprint a kitchen ticket and a receipt | Same numbers and amounts as the original. A reprint is counted and marked as a copy where the template says so. |
| PR-10 | Payment QR on the bill, **off** (the default) | No QR on the bill. |
| PR-11 | Payment QR on the bill, **on**, with the outlet's UPI ID set | The QR is on the unpaid bill only. A UPI app reads the right payee and exactly ₹785. The receipt printed after payment never carries it. With the setting on but no UPI ID, nothing prints. Turn it off again. |
| PR-12 | Split by items | Each bill prints as its own bill with its own number, charges, GST and round off. Every dish is on exactly one of them. |
| PR-13 | Bill paid by two methods | Both payments are listed with their amounts. |
| PR-14 | Credit note | It prints with its own number, the dishes returned, the tax reversed, the refund method, and the original bill's number. |
| PR-15 | X report mid-day, Z report at day end | Totals match the screen and the day's bills. The business date is right. A reprinted Z is identical. |
| PR-16 | Cash drawer | It opens on a cash payment and on "Open drawer", and not on a card-only or UPI-only payment. With "Open the drawer on cash payments" off, it stays shut. |

## Content and layout

| ID | Check | Pass when |
|---|---|---|
| PR-17 | ₹ symbol and special characters | No `?`, boxes or garbled characters. |
| PR-18 | Long dish names and add-ons | They wrap neatly. The price column stays aligned. |
| PR-19 | A dish named in Hindi or Telugu (create a `TEST` dish) | It prints readably, or falls back cleanly. Never garbage. |
| PR-20 | 58 mm paper vs 80 mm paper | Nothing is cut off on either width. |
| PR-21 | Paper cut | The paper cuts after each ticket, with no long blank paper. With auto-cut off, it does not cut. |
| PR-22 | Logo, footer message, second-copy caption | They print as set in Settings. A second copy prints only when a caption is set. |
| PR-23 | Copies of each bill and kitchen ticket set to 2 | Two print. Set back to 1. |
| PR-24 | A 40-line bill | It prints completely, with the totals at the end. |

## When things go wrong

| ID | Check | Pass when |
|---|---|---|
| PR-25 | Printer off when a bill or kitchen ticket is sent | The till says the slip did not go to the printer. The sale or order still completes. The ticket shows "Not printed" on the till. |
| PR-26 | Printer turned back on | Waiting tickets print **once**: not twice, not lost. |
| PR-27 | Printer off for more than a minute, or more than 10 tickets waiting | A "printer down" banner shows on the till screen, with the internet on or off. It clears when the printer recovers. |
| PR-28 | A station's printer fails and a backup printer is set for that route | After three tries the ticket prints on the backup printer, headed as rerouted with the station's name. It does not also print later on the original printer. |
| PR-29 | Paper runs out mid-ticket | Clear warning. After loading paper the ticket can be printed again. |
| PR-30 | Printer cover open | Clear warning. |
| PR-31 | Network cable or Wi-Fi pulled during printing | No crash. A clear message. Recovers after reconnecting. |
| PR-32 | Printer IP changes (router restart) | Behaviour is clear: it reconnects, or tells you exactly what to fix. |
| PR-33 | 20 tickets sent fast (rush hour) | All print, in order, none missing, no mixed lines. |
| PR-34 | Till app restarted with tickets waiting | Waiting tickets print once after the restart, or show a clear option to print. |
| PR-35 | Internet off | Bills, receipts and kitchen tickets print exactly as when online. |
| PR-36 | A kitchen ticket not sent to any printer or screen for 2 minutes | The till shows a banner that a kitchen ticket was not sent. |
