# Script 1 — Owner dashboard

**You are:** the restaurant owner, setting up and running the restaurant from a laptop.
**You need:** the dashboard link and the owner login (sent privately).
**Time:** about 2 hours. You can stop and continue another day.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, tell your AI "O-xx not there".

Name everything you create with `TEST` at the start.

## Sign in and look around

| Step | Do this | Check |
|---|---|---|
| O-01 | Open the dashboard link. Sign in with the owner login. | You land on the home page with your restaurant's name. No other restaurant's name appears anywhere. |
| O-02 | Sign out. Sign in again with a wrong password or wrong code once, then the right one. | The wrong attempt shows a clear message and does not let you in. The right one works. |
| O-03 | Read every box and number on the home page. | Nothing shows `undefined`, `NaN`, `null`, empty boxes or strange numbers. |
| O-04 | Click every item in the side menu, one by one. | Each page opens in about 5 seconds or less, with no error page. Note any page that looks empty or unfinished. |

## Business details

| Step | Do this | Check |
|---|---|---|
| O-05 | Open the business or outlet details. Change the phone number or address to a test value. Save. Refresh the page. | Your change is still there after the refresh. |
| O-06 | Try to save with a required field empty, or a phone number with letters. | A clear message tells you what's wrong. Nothing is saved. |

## Menu

| Step | Do this | Check |
|---|---|---|
| O-07 | Create a category `TEST Drinks`. | It appears in the category list. |
| O-08 | Add an item `TEST Lemon Soda`, price ₹80, in `TEST Drinks`. | It saves. Name, price and category are correct. |
| O-09 | Give the item sizes, e.g. Small ₹80 and Large ₹120. | Both sizes save with the right prices. |
| O-10 | Add an add-on group, e.g. "Extras" with "Mint ₹10" and "Ice ₹0". Try it as optional and as required. | It saves and shows on the item. |
| O-11 | Try to save an item with: no name, a negative price, letters in the price, a very long name (100+ letters). | Each one shows a clear message and is not saved, or is saved sensibly. Nothing breaks the page. |
| O-12 | Change the item price to ₹90. Save. Refresh. | ₹90 is shown after the refresh. |
| O-13 | Mark the item sold out, then available again. | The status changes each time and stays after a refresh. |
| O-14 | Use the search or filter on the menu page. | It finds `TEST Lemon Soda`. |

## Tables

| Step | Do this | Check |
|---|---|---|
| O-15 | Add a section `TEST Patio` and a table `TP1` for 4 people. | Both appear. |
| O-16 | Open the table's QR code. Download or print it if there's an option. | A QR code is shown. Scanning it with your phone opens the menu for that table. |
| O-17 | Try to create a second table with the same name `TP1`. | You get a clear message, or it's handled sensibly. No duplicate confusion. |

## Staff

| Step | Do this | Check |
|---|---|---|
| O-18 | Invite a staff member using the test phone or email the tech team gave you. | The invite shows as pending. The person receives it. |
| O-19 | Look at roles and access. Give the person a role (e.g. cashier or waiter). | The role is saved and shown against the person. |
| O-20 | Open the staff list. Search for a person. | Search finds them. Details are correct. |

## Daily business

| Step | Do this | Check |
|---|---|---|
| O-21 | Open Orders and Billing. Open one order and one bill. | The bill total = items + tax + charges − discount. Times look right (Indian time). |
| O-22 | Open Payments. | Today's payments are listed and match the bills. |
| O-23 | Open Customers. Search by name or phone. Open one. | Search works. You can see their visits or orders. |
| O-24 | Open Reservations. Create a booking for tomorrow, 8 pm, 4 people. Change it to 9 pm. Cancel it. | Each change shows straight away and stays after a refresh. |
| O-25 | Open Inventory. Add a test ingredient (e.g. `TEST Lemons`). Record some stock if there's an option. | It saves with the right quantity and unit. |

## Reports and settings

| Step | Do this | Check |
|---|---|---|
| O-26 | Open Analytics. Switch between today, yesterday and this week. | Numbers change with the dates. Today's sales roughly match today's bills. |
| O-27 | Download or export a report if there's an option. | The file downloads and opens. Numbers match the screen. |
| O-28 | Open Settings. Open each group. Change one harmless setting, save, refresh, then change it back. | Changes stay after a refresh. Every setting's name is understandable. |
| O-29 | Open Audit (history of changes). Find the price change you made in O-12. | It shows what changed, who did it and when. |

## Phone and sign out

| Step | Do this | Check |
|---|---|---|
| O-30 | Open the dashboard on your phone. Try home, menu and orders. | You can read and use them without zooming in or scrolling sideways. |
| O-31 | Sign out. Press the browser's Back button. Refresh. | You cannot see any restaurant data until you sign in again. |

**Done?** Tell your AI: "Finished owner script." Mention any steps you skipped.
