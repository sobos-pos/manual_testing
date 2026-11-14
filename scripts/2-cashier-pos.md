# Script 2 — Cashier POS (web)

**You are:** a cashier at the counter, taking takeaway and table orders on a laptop or tablet.
**You need:** the POS link and the cashier login (sent privately), plus how to pay (the tech team tells you which test payment to use).
**Time:** about 2 hours.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, tell your AI "C-xx not there".

## Sign in

| Step | Do this | Check |
|---|---|---|
| C-01 | Open the POS link. Sign in with the cashier login. | You reach the POS screen for the right outlet. |
| C-02 | Look at the side menu. | You only see what a cashier needs. If you can change staff, salaries, settings or the menu, report it. |
| C-03 | Look at the menu on the POS. | Categories and items load with prices. Sold-out items look different and can't be added. |

## Takeaway orders

| Step | Do this | Check |
|---|---|---|
| C-04 | Start a takeaway. Add 2 different items. Change one quantity to 3. Remove the other. | The total updates correctly every time. |
| C-05 | Add an item with sizes and add-ons: pick Large and one add-on. | The price includes the size and add-on. A required add-on can't be skipped. |
| C-06 | Try to finish the takeaway **without** a customer name. | It asks for the customer's name. |
| C-07 | Enter a name and pay by UPI or card (test payment). | The payment completes. A bill number shows. The order appears in Orders. |
| C-08 | Do another takeaway and try to pay by **cash**. | Either cash works and shows the right change, or a clear message says cash is taken at the till. Anything else is a bug. |
| C-09 | Apply a discount, if allowed. | The total drops by the right amount. Tax is worked out on the right figure. |
| C-10 | Put an order on hold (park it), start another, then bring the first one back. | The held order comes back exactly as it was. |
| C-11 | Cancel an unpaid order. | It is cancelled. It doesn't show as a sale. |
| C-12 | Try to cancel or delete a **paid** bill. | It is not deleted without the right permission or a reason. |

## Mistakes a real cashier makes

| Step | Do this | Check |
|---|---|---|
| C-13 | Click **Pay** twice quickly. | Only one bill and one payment are created. |
| C-14 | Refresh the page in the middle of an order. | Note what happens to the cart. Losing it without warning is a bug. |
| C-15 | Type strange amounts: 0, negative, letters, 1,00,000, or 10.555. | Clear messages. No wrong totals. |
| C-16 | Turn Wi-Fi off for 30 seconds while on the POS, try to add an item, then turn Wi-Fi back on. | A clear message while offline. Nothing doubled or lost after reconnecting. |
| C-17 | Leave the POS untouched for 15–20 minutes, then use it. | Note what happens (signs you out, or works). Losing an order without warning is a bug. |

## Table orders

| Step | Do this | Check |
|---|---|---|
| C-18 | Pick a free table. Add items. Send to kitchen. | The table shows as busy. The order reaches the kitchen screen (ask a teammate to check). |
| C-19 | Add a second round of items to the same table. | It adds to the same table and bill, not a new one. |
| C-20 | Move the table to another free table, if there's an option. | Everything moves. The old table becomes free. |
| C-21 | Make the bill. Split it equally between 2 people and pay each half. | The halves add up to the full bill. Both payments are recorded. |

## After the sale

| Step | Do this | Check |
|---|---|---|
| C-22 | Find an old paid bill (by number or customer). Open or reprint it. | Same items, same amounts and same bill number as the original. |
| C-23 | Do a refund or credit note on part of a bill, if a cashier is allowed to. | The refunded amount is right. The original bill still shows what happened. |
| C-24 | Open any shift or day summary a cashier can see. | Totals match the sales you made today. |
| C-25 | Sign out. Press Back. | You cannot see the POS until you sign in again. |

**Done?** Tell your AI: "Finished cashier script." Mention any steps you skipped.
