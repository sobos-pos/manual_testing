# Printer checklist

**Setup:** a till PC with the till app, at least one receipt printer (80 mm, plus 58 mm if you support it) on USB and on the network if both are supported, and a cash drawer if used. Write down the printer models, the connection type and the printer's IP address before starting.

## What prints

| ID | Check | Pass when |
|---|---|---|
| PR-01 | Customer bill | Restaurant name, GSTIN, address, bill number, date and time (IST), items, quantities, prices, tax lines, total and payment method all match the screen. |
| PR-02 | Kitchen ticket (KOT) | It prints at the right kitchen or station. It shows the table, items, quantities, notes and add-ons. It has no prices if prices aren't meant to show. |
| PR-03 | Kitchen ticket routing | Items from different stations (e.g. bar and kitchen) go to the right printers. |
| PR-04 | Second round KOT | Only the new items print, not the whole order again. |
| PR-05 | Cancelled item after KOT | A cancellation ticket prints, or the kitchen is clearly told. |
| PR-06 | Reprint | The bill number and amounts are the same as the original. It's marked as a copy or duplicate if that's the rule. |
| PR-07 | UPI QR on the bill | The QR scans with a UPI app. It shows the right payee and the exact bill amount. |
| PR-08 | Split bill | Each part prints correctly, and the parts add up to the total. |
| PR-09 | Refund or credit note | It prints with a reference to the original bill. |
| PR-10 | X and Z (day-end) reports | Totals match the bills and payments for the day. The business date is right. |
| PR-11 | Cash drawer | It opens on a cash sale only, not on UPI or card sales. |

## Content and layout

| ID | Check | Pass when |
|---|---|---|
| PR-12 | ₹ symbol and special characters | No `?`, boxes or garbled characters. |
| PR-13 | Long item names and add-ons | They wrap neatly. The price column stays aligned. |
| PR-14 | Regional language item names (if supported) | They print readably, or fall back cleanly. |
| PR-15 | 58 mm paper vs 80 mm paper | Nothing is cut off on either width. |
| PR-16 | Paper cut | The paper cuts after each ticket, with no long blank paper. |
| PR-17 | Logo (if configured) | It's clear and doesn't slow printing badly. |

## When things go wrong

| ID | Check | Pass when |
|---|---|---|
| PR-18 | Printer off when a bill or KOT is sent | The till shows a clear warning. The sale still completes. |
| PR-19 | Printer turned back on | Queued tickets print **once**, not twice and not lost. |
| PR-20 | Paper runs out mid-ticket | Clear warning. After loading paper you can reprint. |
| PR-21 | Printer cover open | Clear warning. |
| PR-22 | Network cable or Wi-Fi pulled during printing | No crash. A clear message. Recovers after reconnecting. |
| PR-23 | Printer IP changes (router restart) | Behaviour is clear: it reconnects, or tells you exactly what to fix. |
| PR-24 | Two tills sending to one printer at the same moment | Both tickets print fully, with no mixed lines. |
| PR-25 | 20 tickets sent fast (rush hour) | All print, in order, none missing. |
| PR-26 | Till app restarted with tickets waiting | Waiting tickets print once after the restart, or show a clear option to reprint. |
