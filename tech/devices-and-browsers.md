# Devices and browsers checklist

Run the main flows on each combination. Record the device model, the operating system and the browser or app version in each bug.

Main flows: sign in → menu → order → bill → pay, using **order A** (₹785) so the figures can be checked.

## The till

| ID | Where | Pass when |
|---|---|---|
| DB-01 | Till PC at 1366×768, at 1920×1080, and on a touch screen | Nothing is cut off. The bill panel, the totals and the Settle button are always visible without scrolling sideways. Buttons are big enough to tap. No action needs a mouse hover. |
| DB-02 | Keyboard only at the till | F3 opens tables, F2 takeaway. `/` jumps to the dish search. Enter adds the first match. F8, F9 and F10 choose a payment method. Ctrl+B folds the side menu. A whole takeaway sale can be made without the mouse. |
| DB-03 | The oldest, slowest PC a pilot outlet will use | The till starts in under a minute, unlocks in under 2 seconds, and adding a dish feels instant. |
| DB-04 | Windows display scaling at 125% and 150% | Still usable. Text is not clipped. |
| DB-05 | The till left running for 12 hours with a full day of sales | No slowdown. No growing memory warning. |

## The kitchen display

| ID | Where | Pass when |
|---|---|---|
| DB-06 | A second monitor or TV, landscape, read from 2 metres | Table, dishes and quantities are readable. Colour is not the only sign that a ticket is late: the word is shown too. |
| DB-07 | A touch screen | Bump is easy to tap and hard to tap by accident. |

## The waiter app

| ID | Where | Pass when |
|---|---|---|
| DB-08 | Android 10, a mid-range current phone, and the newest Android | Installs, signs in, finds the till, and stays quick through a full service. |
| DB-09 | A small phone (5 inches) and a large one | Readable. Nothing overlaps. The Send and Settle buttons are never hidden by the keyboard. |
| DB-10 | Battery saver on; app in the background for 10 minutes | Notifications for a guest order, a guest request and food ready still arrive. The app resumes on the right screen. |
| DB-11 | Phone on mobile data instead of the restaurant's Wi-Fi | It says clearly that it cannot reach the till. It does not pretend to work. |
| DB-12 | The phone's local-network permission refused | The app explains what to allow and why. |
| DB-13 | Font size set to largest in Android settings | Still usable. |

## The dashboard

| ID | Where | Pass when |
|---|---|---|
| DB-14 | Chrome, Edge and Firefox on Windows. Safari on Mac if available | Everything works and looks the same. |
| DB-15 | Laptop 1366×768, desktop 1920×1080, tablet in both orientations, phone | No cut-off content. No sideways scrolling. Tables of data are readable. |
| DB-16 | Browser zoom at 125% and 150% | Still usable. |
| DB-17 | Keyboard only: Tab, Enter, Escape | Every form and dialog can be completed and closed. Focus is always visible. |

## The guest pages

| ID | Where | Pass when |
|---|---|---|
| DB-18 | Android Chrome on a cheap phone and a new phone; iPhone Safari | Menu, cart, pairing (camera scan and typed code), one-time code and ordering all work. The keyboard never hides the button you need. |
| DB-19 | A 360 px wide screen and a large phone | Readable. No overlapping parts. |
| DB-20 | Scan the table QR with the phone camera, Google Lens, a UPI app's scanner, and from inside WhatsApp | The menu opens each time. |
| DB-21 | Camera permission refused when scanning the waiter's code | The guest is offered the typed code or table PIN instead. |
| DB-22 | Weak 4G, and public Wi-Fi with a sign-in page | The menu is usable within a few seconds on weak 4G. Clear messages when slow. Never a spinner past about 5 seconds. |
| DB-23 | The booking page on phone and laptop | Works on both. |

## Everywhere

| ID | Where | Pass when |
|---|---|---|
| DB-24 | Dark mode on the device | Text is readable, or the app stays in light mode cleanly. |
| DB-25 | Amounts, dates and times on every surface | Rupees written the Indian way (₹1,00,000.00). One date and time format. Indian time. |
