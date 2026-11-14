# Script 3: Waiter app

**You are:** Wasim, a waiter on the floor, using the waiter app on an Android phone.
**You need:** the waiter app, your waiter login, a phone on the same Wi-Fi as the till, and [the test restaurant page](../TEST-RESTAURANT.md). The till must be running with its cash drawer open.
**Teammates:** a customer (script 5) for section 4, the kitchen (script 4) for section 5, and a manager for W-33 and W-34. If nobody is free, mark those steps blocked.
**Time:** about 2.5 hours.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, say "W-xx not there". If you can't do a step, say "W-xx blocked".

**Cash sheet.** When you take cash from a guest, tell your AI, e.g. *"Cash: Order A table 4, 785, handed to counter."*

## 1. Start of shift

| Step | Do this | Check |
|---|---|---|
| W-01 | Open the app. Enter your phone number and ask for a code. | The code arrives by SMS (or WhatsApp) within about a minute. The message on screen does not say whether the number is staff or not. |
| W-02 | Enter a wrong code once, then the right one. | The wrong code is refused clearly. The right one signs you in. |
| W-03 | Choose your outlet, if asked. | Main Outlet is shown. You see no other restaurant's outlets. |
| W-04 | Connect to the till: Profile → Settings → Find till. | The till is found by itself within a few seconds. It shows Connected, and names the main computer. You did not have to type an address. |
| W-05 | Before clocking in, try to open a table. | You are told to clock in first. |
| W-06 | Clock in. | It shows you are on shift, with the right time (Indian time). |
| W-07 | Look at the tabs. | Floor, Orders, Kitchen, Requests and Profile. Nothing for menu prices, staff or settings. |

## 2. The floor

| Step | Do this | Check |
|---|---|---|
| W-08 | Open Floor. Compare it with the till's floor. | The same tables, in Main Hall and Rooftop, with the same states (available, occupied, cleaning) as the till shows. A table changed on the till changes here within a few seconds. |
| W-09 | Switch between your own tables and all tables. | "Mine" shows only tables assigned to you or that you opened. All shows every table. |
| W-10 | Open free table 4. Enter 2 guests. | The table opens. It shows as occupied here and on the till. |
| W-11 | Open a table that is still Cleaning. | You are asked whether to seat anyway, and for a reason. With a reason the table opens. Without one it does not. |

## 3. Taking an order

| Step | Do this | Check |
|---|---|---|
| W-12 | On table 4, add **order A** (1 Butter Chicken, 2 Butter Naan, 1 Jeera Rice). Use search for one dish and the Veg filter for another. | Search finds dishes by part of the name. The Veg filter hides non-veg dishes. Prices match the price list. |
| W-13 | On the Butter Chicken, choose a spice level and add the note "less oil". | The choice and the note show on the line. |
| W-14 | Open the cart. | Three lines, right quantities, total before tax ₹680. |
| W-15 | Send to Kitchen. | "Sent to the kitchen." The kitchen display shows the order with the spice level and your note. Butter Naan shows at the Tandoor. |
| W-16 | Tap Send twice very quickly on a second round (1 Masala Chai). | The chai goes once, not twice. |
| W-17 | Open the table. Look at its rounds. | Both rounds are listed under "In the kitchen", with a running total. |
| W-18 | Open table R2 on the Rooftop and add 1 Butter Chicken. | The price is ₹400, not ₹360. Cancel it or close the table again. |
| W-19 | Hold a dish on the menu (e.g. Rasmalai) and mark it sold out. | It is marked sold out here, on the till and on the customer's menu within a few seconds, and cannot be added. |
| W-20 | Bring it back from the Sold out list. | It can be ordered again everywhere. |

## 4. Guests ordering from their phones

Needs a teammate playing the customer (script 5).

| Step | Do this | Check |
|---|---|---|
| W-21 | Open table 3 with 2 guests. Open "Pair a guest device". Show the code to the customer. | A QR and a table PIN are shown clearly. The QR refreshes by itself while the screen is open. |
| W-22 | The customer scans the QR (or types the PIN). | Your app says a device was paired to table 3 and shows how many devices are paired. |
| W-23 | Wait 3 minutes with the pairing screen closed, then ask a second customer to use a photo of the old QR. | It is refused: the code has expired. A fresh code from your screen works. |
| W-24 | Rotate the code while a customer is about to scan the old one. | The old code stops working at once. |
| W-25 | The customer places **order G round 1** (2 Masala Dosa, 2 Filter Coffee). | You get a notification for your table. The round is under "Awaiting your review". **Nothing is on the kitchen display yet.** |
| W-26 | Open the round and accept it. | The kitchen ticket fires now. The customer's phone shows it was accepted. |
| W-27 | The customer orders again. Reject this round with a reason ("out of stock"). | A reason is required. The customer's phone shows it was not accepted, with your reason. Nothing reaches the kitchen. |
| W-28 | The customer orders **round 2** (1 Rasmalai). Do not accept it for 2 minutes. | After 90 seconds the table on your floor shows "Order waiting" with the minutes. It clears when you accept. Accept it. |
| W-29 | The customer taps Call server, Ask for water and Ask for the bill. | Each arrives in Requests within a few seconds, with the right table. You can mark it in progress, then completed. |
| W-30 | The customer taps "Ready to order". | Requests shows "Table 3 is ready to order". |
| W-31 | Unpair all guest devices, with a reason. | The customer can no longer order until paired again. |

## 5. Serving and changing

Needs the kitchen teammate (script 4) for W-32.

| Step | Do this | Check |
|---|---|---|
| W-32 | Ask the kitchen to mark your order ready. Open "Ready to serve". | You are notified. The order is listed as ready. Mark it served, and confirm. It moves to Served. |
| W-33 | On table 4, cancel the Masala Chai that already went to the kitchen. | You must pick a reason, and it asks for a **manager's PIN** on your phone. With the manager's PIN it is cancelled and the kitchen is told. Without it, nothing changes. |
| W-34 | Try to cancel table 4's whole order. | It also needs a reason and a manager's PIN. Don't complete it. |
| W-35 | Add a kitchen note to a sent dish. | The kitchen sees the note. The bill does not change. |
| W-36 | Open the Kitchen tab. | You can see the kitchen's tickets but cannot change them. |
| W-37 | Open table 1 with 2 guests and send 2 Masala Chai. From table options, move the table to free table 8. | The order and total move to table 8. Table 1 is released. |
| W-38 | Join free table 7 to table 8, then un-join it. | Both show as one party while joined. Table 7 is released after. |
| W-39 | Open table 2 and send 1 Filter Coffee. Move 1 Masala Chai from table 8 to table 2. | The chai leaves table 8's total and appears on table 2's. Nothing is lost or doubled. |

## 6. The bill and the payment

| Step | Do this | Check |
|---|---|---|
| W-40 | Table 4 now holds exactly **order A** (the chai was cancelled). Prepare its bill while some food is still not marked served. | You are warned that some food is not served yet, and can go back or carry on. |
| W-41 | Prepare the bill. | Subtotal ₹680, service charge ₹68, tax ₹37.40, round off −₹0.40, **To pay ₹785**. The same figures as on the till. |
| W-42 | Choose Cash and settle. | You are told to hand ₹785 to the Front Counter. The table closes. The till shows the bill as paid. Tell your AI the cash line, and hand the play money to the cashier. |
| W-43 | Prepare table 3's bill (**order G**: the two rounds you accepted) and pay by Card. | **To pay ₹681** (Subtotal ₹590, service charge ₹59). The rejected round is not on it. It settles, and nothing is added to the cash drawer. |
| W-44 | Prepare the bills for tables 2 and 8 and pay each by UPI. | No QR is shown on the phone (see known limits). You confirm the guest has paid, and each settles as UPI. |
| W-45 | Look at the payment methods offered. | Only Cash, Card and UPI. Nothing the outlet doesn't take. |
| W-46 | Tap Settle twice very quickly. | The bill is paid once. |
| W-47 | Reprint the kitchen ticket for a table's last round. | "Reprint sent to the till." |
| W-48 | After the guests leave, mark Guests left, then Mark clean & available. | The table goes to Cleaning, then free, here and on the till. |
| W-49 | Open table 5, add nothing, and close the table. | It closes with no bill. |

## 7. Takeaway from the phone

| Step | Do this | Check |
|---|---|---|
| W-50 | Start a takeaway. Add **order T1** (1 Chicken Biryani, 1 Sweet Lassi). Try to pay without a guest name. | It asks for the name. The pay button stays off until a name is entered. |
| W-51 | Enter `TEST Suresh`, no phone. Review and pay by UPI. | **To pay ₹483**, with ₹10 packaging and no service charge. After payment you see Paid, an invoice number, and the kitchen gets the order. |
| W-52 | Repeat with a phone number of 9 digits, then 10 digits. | 9 digits is refused clearly. 10 digits is accepted. |

## 8. Real life

| Step | Do this | Check |
|---|---|---|
| W-53 | Lock the phone for 5 minutes in the middle of an order, then unlock. | The app is where you left it. Nothing is lost or sent twice. |
| W-54 | Turn the phone's Wi-Fi off. Build a round and send it. Turn Wi-Fi on. | While off, a clear message says the phone can't reach the till, and the round waits. After reconnecting it goes once. |
| W-55 | Walk to a weak-signal corner and send a round. | It either goes, or clearly waits. Never a spinner with no message, never a double order. |
| W-56 | Ask the tech team to switch the till off for a minute. | The app says it can't reach the restaurant computer. When the till is back it reconnects by itself and the floor is right. |
| W-57 | Use the app on the smallest phone you have, and turn it sideways. | Everything is readable. Buttons are easy to tap. |
| W-58 | Close the app completely and open it again. | You are still signed in and on shift. The floor loads within a few seconds. |

## 9. Your own things

| Step | Do this | Check |
|---|---|---|
| W-59 | Open your roster, shift details and performance. | They show your own information only. |
| W-60 | Apply for a day's leave. | It is saved and shows as waiting for approval. |
| W-61 | Open notifications and Help. | Your notifications are listed, newest first. Help opens. |
| W-62 | Try to sign out while still clocked in. | You are warned that you're still clocked in, and offered to clock out and sign out. |
| W-63 | Clock out and sign out. | The clock-out time is right. You cannot see tables or orders until you sign in again. |

**Done?** Tell your AI: "Finished waiter script." Mention any steps you skipped or that were blocked.
