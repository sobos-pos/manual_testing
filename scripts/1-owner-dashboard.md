# Script 1: Owner

**You are:** Rohan, the restaurant owner. You set the restaurant up, and you watch the money, the stock and the staff from a laptop.
**You need:** the dashboard link and the owner login (sent privately), and [the test restaurant page](../TEST-RESTAURANT.md).
**Teammates:** a cashier at the till for O-44 and O-51. A new staff member with their own phone for O-29 to O-35. A waiter for O-27.
**Time:** about 3 hours. Sections 1 to 6 on the first day; sections 7 to 11 on a later day, after the others have sold something.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, say "O-xx not there". If you can't do a step, say "O-xx blocked".

**Never change the standard menu, tables, staff or settings.** Everything you create or change starts with `TEST`. Other testers are checking totals against the standard prices while you work.

## 1. Sign in and look around

| Step | Do this | Check |
|---|---|---|
| O-01 | Open the dashboard link. Sign in with a wrong password once, then the right one. If asked for a code from an authenticator app, enter it. | The wrong attempt is refused with a clear message that doesn't say whether the account exists. The right one lets you in. |
| O-02 | Look at the home page. | It shows your restaurant's and outlet's name. No other restaurant's name appears anywhere. |
| O-03 | Read every box and number on the home page. | Nothing shows `undefined`, `NaN`, `null`, empty boxes or strange numbers. Amounts are in rupees, written the Indian way (₹1,00,000). |
| O-04 | Click every item in the side menu, one by one, and every tab on each page. | Each opens in about 5 seconds or less, with no error page. Note any page that looks empty or unfinished. |
| O-05 | Open the notification bell. | Notifications are real events (a waiting order, low stock), newest first. Opening one takes you to the right place. |

## 2. Business details

| Step | Do this | Check |
|---|---|---|
| O-06 | Open Business & Branches. Open the outlet's details. | Legal name, GSTIN, FSSAI number and address are shown. These print on every bill. |
| O-07 | Add the word `TEST` to the end of the address line. Save. Refresh. | The change is still there. Change it back. |
| O-08 | Try to save a GSTIN with a wrong length or a phone number with letters. | A clear message says what is wrong. Nothing is saved. |
| O-09 | Open the outlet's opening hours. Look, don't change. | Every day has hours, and they match when the restaurant is open. |
| O-10 | Open Bank accounts and start to edit one. | You are asked to confirm it's you again (code or password) before you can change bank details. Cancel without saving. |

## 3. Menu

| Step | Do this | Check |
|---|---|---|
| O-11 | Open Menu & Recipe. Check five dishes against the price list. | Names, prices and categories match the test restaurant page. |
| O-12 | Create a category `TEST Drinks`, sent to the Beverage Bar. | It appears in the category list. |
| O-13 | Add an item `TEST Lemon Soda` in `TEST Drinks`: vegetarian, GST 5%, price ₹80. | It saves. Name, price, category and tax are right. |
| O-14 | Give it two sizes: Small ₹80 and Large ₹120. | Both sizes save with the right prices. |
| O-15 | Add an optional add-on group `TEST Extras` with Mint ₹10 and Ice ₹0. Attach it to the item. | It saves and shows on the item. |
| O-16 | Add a second add-on group `TEST Taste` with Sweet and Salted, where the guest **must** pick one. Attach it. | It saves as required, with "pick exactly one". |
| O-17 | Upload a photo for the item. | The photo shows on the item, and on the customer's menu within a minute. |
| O-18 | Give the item the short code `TLS`. Then try the same short code on a second `TEST` item. | The first saves. The second is refused: the code is already taken. |
| O-19 | Try to save an item with: no name, a negative price, letters in the price, a price above ₹1,00,000, a name of 200 letters. | Each one shows a clear message and is not saved. Nothing breaks the page. |
| O-20 | Change the Small price to ₹90. Save. Refresh. | ₹90 is shown after the refresh. The till and the customer's menu show ₹90 within a minute or two. |
| O-21 | Mark the item sold out, then available again. | The status changes each time, stays after a refresh, and reaches the till and the customer's menu. |
| O-22 | Open the Rooftop price list. Give `TEST Lemon Soda` (Small) a Rooftop price of ₹100. | It saves. A Rooftop table sells it at ₹100, a Main Hall table at ₹90. |
| O-23 | Search the menu for "lemon". Filter by category. | It finds `TEST Lemon Soda`. Filters work. |

## 4. Tables

| Step | Do this | Check |
|---|---|---|
| O-24 | Open Tables & Floor. Add a section `TEST Patio` and a table `TP1` for 4 people in it. | Both appear here, and on the till's and waiter app's floor within a minute or two. |
| O-25 | Try to create a second table called `TP1`. | Refused with a clear message. |
| O-26 | Open QR stickers. Open `TP1`'s QR. Scan it with your phone. | Your phone opens the menu for table TP1. The link has no table number you could guess, only a random code. |
| O-27 | Open Assignments. Assign `TP1` to one waiter. | The waiter sees `TP1` among their own tables. A customer scanning `TP1` is shown that waiter as their server. |
| O-28 | Open the Status board while a teammate has tables open. | It shows the same tables as seated as the till does. Tables run by the till are shown for watching, not for editing. |

## 5. Staff

| Step | Do this | Check |
|---|---|---|
| O-29 | Open Staff & Access. Invite a new staff member `TEST Kiran` as a Waiter, using the test phone number the tech lead gave you. | The invite shows as pending. The person gets an SMS with a link. |
| O-30 | Ask that person to open the link, give their name, then sign in to the waiter app with their phone and a code. | They get in as a waiter at Main Outlet, and see nothing an owner sees. The invite no longer shows as pending. |
| O-31 | Ask them to open the same invite link again. | It no longer works. |
| O-32 | Set a till PIN for `TEST Kiran`. Try a PIN that another person already uses. | The PIN saves and works on the till within a minute or two. A PIN already in use is refused. |
| O-33 | Open Roles & permissions. Create a role `TEST Captain` by copying Waiter and adding "apply a discount". Give it to `TEST Kiran`. | The role saves. On the till or waiter app, `TEST Kiran` can now discount, at their next action. |
| O-34 | Invite a second person, then cancel that invite before they use it. | The link stops working. |
| O-35 | Remove `TEST Kiran`'s access. | They are signed out or refused at their next action in the waiter app, and their till PIN stops working. |
| O-36 | Open Staff & Management → Roster. Add a shift for a waiter tomorrow, 11 am to 4 pm. Try to add an overlapping shift for the same person. | The shift saves and shows in the waiter's app. The overlap is refused or clearly warned. |
| O-37 | Open Attendance, Leave and Payroll. | Today's clock-ins are listed with the right times. Leave requests are listed. Payroll opens for the owner. |

## 6. Stock

| Step | Do this | Check |
|---|---|---|
| O-38 | Open Inventory. Add an ingredient `TEST Lemons`, counted in pieces. | It saves, with stock 0. |
| O-39 | Add a supplier `TEST Fruit Supplier`. | It saves. |
| O-40 | Raise a purchase order to that supplier: 100 `TEST Lemons` at ₹5 each. | The order totals ₹500 and shows as waiting for goods. Stock is still 0. |
| O-41 | Receive the goods: all 100. | Stock is now 100. The movement list shows +100 with the purchase order. |
| O-42 | Record a payment of ₹500 to the supplier. | The supplier's balance due goes to ₹0. |
| O-43 | Open `TEST Lemon Soda`'s recipe. Set it to use 2 `TEST Lemons` per glass. | It saves. A cost per glass is shown (₹10). |
| O-44 | Ask the cashier to sell 3 `TEST Lemon Soda` on the till and send them to the kitchen. Wait a minute or two. | Stock falls to 94. The movement list shows the sale. |
| O-45 | Record 4 lemons as wastage, with a reason. | Stock is 90. A reason is required. |
| O-46 | Do a stock count: enter 88. | It shows a difference of −2 and what that is worth (₹10). After it is accepted, stock is 88 and the difference is recorded, not hidden. |
| O-47 | Raise a second purchase order for 50 lemons. Receive only 30. Then close the order with a reason. | Stock is 118. The order shows as closed, with ordered 50 and received 30. It cannot be received against again. |
| O-48 | Look at the Overview and any low-stock list. | Figures match what you just did. Nothing shows a balance that differs from its movements added up. |

## 7. The day's business

Do this section after other testers have sold on the till.

| Step | Do this | Check |
|---|---|---|
| O-49 | Open Orders & Billing → Live orders while a teammate is serving. | Open orders appear and change as they are served and paid, without refreshing. Orders taken on the till can be watched but not edited here. |
| O-50 | Open Bills. Search for one bill by its number, then filter by date, amount, payment method and status. | Each search finds the right bills, across more than one day. |
| O-51 | Open the bill for a standard order (ask the cashier for order A's bill number). | Dishes, service charge, GST, round off and **₹785** match the test restaurant page. The time is Indian time. The payment method is right. |
| O-52 | Open Credit notes, Day end, Shifts and Expenses. | Each lists what the testers did: credit notes with reasons, the day's totals, each drawer with its float and count, each pay out with its expense head. |
| O-53 | Open Payments & Tenders. | It shows which payment methods the outlet takes and whether online payment is connected. No keys or secrets are shown. |
| O-54 | Open Customers & Engagement → Guests. Search by name, then by phone. Open one guest. | Search works. You see their visits and spend, and up to three favourite dishes. |
| O-55 | Open Reservations. Create a booking for tomorrow, 8 pm, 4 people. Change it to 9 pm. Cancel it. | Each change shows straight away and stays after a refresh. A booking for 13 people or a past date is refused. |
| O-56 | Create a booking for today, 30 minutes from now, for 2. When the time comes, mark the party as arrived and seat it at a table. | The booking shows as seated at that table. The table shows as seated on the till. |
| O-57 | Open Availability and Waitlist. Add a walk-in party of 3 to the waitlist. | Availability shows free and booked slots. The party is on the waitlist with its position. |

## 8. Reports

| Step | Do this | Check |
|---|---|---|
| O-58 | Open Analytics & Reports. Open the sales summary for today. | Net sales, tax, charges, discounts, round off and total collected are shown. Ask your AI for the testers' totals for today: they match. |
| O-59 | Switch between today, yesterday, this month and a custom range. Compare two periods. | Numbers change with the dates. A day with no sales shows zero, not an error. |
| O-60 | Open the reports for top dishes, payment methods and sales by staff. | Cash, card and UPI totals match the till's X report. Each waiter's sales are their own tables. |
| O-61 | Open the leakage figures: KOT voids, cancelled after KOT, bill voids, credit notes, discounts. | Every void, walk-out, cancelled dish, discount and credit note the testers made is counted, with amounts. |
| O-62 | Export a report. Open the file. | It downloads and opens in Excel. The numbers match the screen. Dish names with special characters read correctly. |
| O-63 | Save a report view, leave the page and come back. | The saved view is there and opens with the same filters. |

## 9. Settings and devices

| Step | Do this | Check |
|---|---|---|
| O-64 | Open Settings. Open each group. | Every setting has a name and a short explanation you can understand without help. No setting shows a code name. |
| O-65 | Open Order reasons. Add a cancel reason `TEST Wrong dish`. | It saves. On the till, it appears in the reason list within a minute or two. Remove it afterwards. |
| O-66 | Open Number series. Look at the bill number format and the outlet's invoice code. | The format gives numbers of 16 characters or fewer. The invoice code is 3 letters or digits, and cannot be changed now that bills exist: the page says why. |
| O-67 | Try to make the bill number format longer than 16 characters. | Refused, with the reason. Nothing is saved. |
| O-68 | Open Node & Devices. | The till shows as online, with when it was last seen. Its counter, printers, kitchen stations and print routes are listed. Any alert (printer down, till offline) is shown in plain words. |
| O-69 | Open Integrations. | Each connection shows whether it is on and working. No password, key or token is shown. |

## 10. History of changes

| Step | Do this | Check |
|---|---|---|
| O-70 | Open Audit & Compliance → Audit trail. Find the price change from O-20. | It shows the old price, the new price, who changed it and when. |
| O-71 | Find the role you created (O-33) and the access you removed (O-35). | Both are recorded with your name. |
| O-72 | Try to edit or delete an audit entry. | There is no way to. |

## 11. Phone and sign out

| Step | Do this | Check |
|---|---|---|
| O-73 | Open the dashboard on your phone. Try home, bills and reports. | You can read and use them without zooming in or scrolling sideways. |
| O-74 | Open your account's devices. | Your laptop and your phone are listed. You can sign one out from the other. |
| O-75 | Sign out. Press the browser's Back button. Refresh. | You cannot see any restaurant data until you sign in again. |

**Done?** Tell your AI: "Finished owner script." Mention any steps you skipped or that were blocked.
