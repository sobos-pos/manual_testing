# Script 2: Cashier at the till

**You are:** Priya, the cashier at the Front Counter. You take takeaway orders, bill the tables and look after the cash drawer.
**You need:** the till PC with the till app (the tech team sets it up), your own till PIN, play money, and [the test restaurant page](../TEST-RESTAURANT.md) open beside you.
**Time:** about 3 hours. You can stop and continue another day, but do sections 2 and 10 (open and close the drawer) on the same day.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, say "C-xx not there". If you can't do a step because something isn't set up, say "C-xx blocked".

**Printing is the tech team's job.** You don't check the paper. But if the till says a slip did not print, the sale must still go through, and the message must be clear.

**Cash sheet.** Every time cash goes into or out of the drawer, tell your AI in one line, e.g. *"Cash: T1, 483, given 500, change 17."*

**Free the tables as you go.** After a table is paid, mark the guests as left and the table clean (step C-34), so it is free for later steps.

## 1. Start of the day

| Step | Do this | Check |
|---|---|---|
| C-01 | Start the till. Look at the lock screen. | It shows the outlet's name, the time and date (Indian time), whether the till is online, and "Enter your PIN". |
| C-02 | Type a wrong PIN once. | It is refused with a clear message. You are not let in. (Don't do this more than twice: five wrong PINs lock you out.) |
| C-03 | Type your own PIN. | "Welcome back" with your name, then the till opens on **Billing**. |
| C-04 | Look at the side menu. | You see Billing, Guest orders, Today's bills, Cash drawer and Kitchen. If you can change the menu's prices, staff, salaries or settings, report it. |
| C-05 | Lock the till, then unlock it with your PIN. | It locks at once and opens again for you. |
| C-06 | Leave the till untouched for 6 minutes. | It locks by itself after about 5 minutes. Nothing you were doing is lost when you unlock. |

## 2. Open the cash drawer

| Step | Do this | Check |
|---|---|---|
| C-07 | Before opening the drawer, start a takeaway, add any dish and try to take payment. | You are told to open the cash drawer first. No sale is made. Clear the ticket. |
| C-08 | Open **Cash drawer**. Count ₹2,000 of play money into the drawer. Enter an opening float of ₹2,000 and open the drawer. | "Drawer opened." Opening float shows ₹2,000. Expected in drawer shows ₹2,000. Tell your AI: *"Cash: float 2000."* |
| C-09 | Try to open a second drawer, or enter a float with letters or a minus sign. | Refused with a clear message. Still one drawer, ₹2,000. |

## 3. Takeaway

| Step | Do this | Check |
|---|---|---|
| C-10 | Go to Billing → Takeaway. Add **order T1** (1 Chicken Biryani, 1 Sweet Lassi). | Subtotal ₹450.00, a ₹10.00 charge for packaging, GST ₹23.00, **To pay ₹483**. No service charge. |
| C-11 | Try to charge without a customer name. | It asks for the name. Nothing is charged. |
| C-12 | Enter the name `TEST Ravi`, leave the phone empty. Choose Cash. Enter ₹500 as cash given. | "Give back" shows **₹17**. |
| C-13 | Confirm the payment. | The sale completes. You see a bill number and a pickup token. The ticket reaches the kitchen display (ask the kitchen teammate, or look at Kitchen). Tell your AI the cash line. |
| C-14 | Add **order T2** (1 Masala Dosa with Cheese, 1 Filter Coffee) for `TEST Anita`, with a 10-digit phone number. | Subtotal ₹260.00, packaging ₹10.00, GST ₹13.50, round off +₹0.50, **To pay ₹284**. |
| C-15 | Choose UPI. If a QR appears, look at it; then use "Guest paid by UPI · mark paid". | Any QR shows exactly ₹284 and a countdown. After marking paid, the sale completes with a new bill number and token. |
| C-16 | Add **order T3** (4 Chicken Biryani, 2 Veg Biryani, 6 Gulab Jamun) for `TEST Office`. | **To pay ₹2,783.** |
| C-17 | Choose Card. Type a slip number and an approval code (any test values). Confirm. | It reminds you to confirm only once the card machine has approved. The sale completes. |
| C-18 | Start a takeaway, add 2 dishes, and **hold** the ticket. Start another takeaway and pay it. Then open Held tickets and recall the first. | The held ticket comes back with the same dishes, quantities and customer. Pay it or discard it. |
| C-19 | Type part of a dish name in the search box and press Enter. | The first match is added. Search finds dishes by any part of the name. |
| C-20 | If the owner has given `TEST Lemon Soda` the short code `TLS` (step O-18), type `TLS`. | That dish is listed first. |
| C-21 | Look at the Recent strip, if there is one. | It shows dishes that sell often. Tapping one adds it. |
| C-22 | Add a dish, change its quantity to 3, then remove it. Add a dish with a size (Tandoori Chicken: Half, then Full). | The total updates correctly each time: Half ₹320, Full ₹580. |
| C-23 | Tap **Charge** twice very quickly on a small takeaway order (pay by UPI, mark paid). | Only one bill and one token are created. Check in Today's bills. |

## 4. A table, start to finish

| Step | Do this | Check |
|---|---|---|
| C-24 | Go to Billing → Tables. Look at the floor. | Main Hall (tables 1–8) and Rooftop (R1–R4) are shown. Each table shows its real state: free, seated, bill printed, paid or cleaning. |
| C-25 | Tap free table 4. Enter 2 guests. Seat them. | "Table opened." Table 4 now shows as seated, with 2 guests and how long ago. |
| C-26 | Add **order A** (1 Butter Chicken, 2 Butter Naan, 1 Jeera Rice). Don't send it yet. | The dishes sit under "New items". Settle is not available yet. |
| C-27 | Send to the kitchen. | The dishes move to "Sent to the kitchen" with a kitchen ticket number. The kitchen display shows them: Butter Chicken and Jeera Rice at Main Kitchen, Butter Naan at Tandoor. |
| C-28 | Add 1 Gulab Jamun as a second round and send it. | It goes to the same table as a new kitchen ticket. Only the Gulab Jamun is new for the kitchen, not the whole order again. |
| C-29 | Remove the Gulab Jamun again (cancel that one dish). | It asks for a reason. The kitchen is told. The table's total drops by ₹120. |
| C-30 | Add a kitchen note to a dish that was already sent: "less spicy". | The kitchen gets the note. The bill does not change. |
| C-31 | Make the bill (Print bill). | The bill shows Subtotal ₹680.00, service charge ₹68.00, GST ₹37.40, round off −₹0.40, **To pay ₹785**. The table shows "Bill printed". |
| C-32 | Settle. Choose Cash. Enter ₹800. | "Give back" shows **₹15**. |
| C-33 | Confirm. | "Bill settled" with an invoice number. Table 4 shows Paid. Tell your AI the cash line. |
| C-34 | On the floor, mark that the guests have left, then mark the table clean. | The table goes to Cleaning, then to free. |

## 5. Discounts and the service charge

| Step | Do this | Check |
|---|---|---|
| C-35 | Seat table 3 with 3 guests. Add **order E** (2 Mutton Biryani, 1 Chicken Tikka, 2 Mango Lassi). Send it. Make the bill. | **To pay ₹1,640** (Subtotal ₹1,420.00, service charge ₹142.00, GST ₹78.10). |
| C-36 | Open "Discount or void" on the bill. Apply a 10% discount with a reason. | "Discount applied." The discount is ₹142.00. No manager is needed (it is under ₹500). |
| C-37 | Read the new total. | **To pay ₹1,476** (service charge ₹127.80, GST ₹70.30). If you see ₹1,491, report it once: it is open question OQ-1 in [known limits](../KNOWN-LIMITS.md). |
| C-38 | Try a discount of 150%, a discount bigger than the bill, and a minus amount. | Each is refused with a clear message. The bill never goes below zero. |
| C-39 | Pay order E by Card. | Settled. |
| C-40 | Seat table 5. Add **order A** again. Send it. Make the bill (₹785). The guest refuses the service charge: use "Waive service charge" with a reason. | No manager is needed. The service charge and its GST both go. **To pay ₹714.** |
| C-41 | Pay it by UPI (mark paid). | Settled at ₹714. |
| C-42 | Seat table 7 with 6 guests. Add **order D** and send it. Make the bill (**₹3,107**). Try a flat discount of ₹600. | The till says it needs a manager and asks for a manager's PIN. Without the PIN, the discount is not applied. Cancel the discount. |

## 6. Paying in parts

| Step | Do this | Check |
|---|---|---|
| C-43 | Settle order D on table 7 with two methods: ₹2,000 cash and the rest by UPI. | After the cash, "Still to pay" shows **₹1,107**. After the UPI, the bill is settled once, with one invoice number, and both payments are listed. Tell your AI: *"Cash: Order D, 2000."* |
| C-44 | Seat table 2 with 3 guests. Add **order C** (1 Paneer Butter Masala with Extra butter, 1 Dal Makhani, 4 Tandoori Roti, 2 Fresh Lime Soda). Send it. Make the bill. | **To pay ₹1,086.** The Extra butter adds ₹30. |
| C-45 | Split the payment equally between 3 guests. | Three shares of **₹362** each. They add up to ₹1,086. |
| C-46 | Pay the three shares: one cash, one card, one UPI. | One bill, three payments. The table shows Paid only after the third. Tell your AI: *"Cash: Order C share, 362."* |
| C-47 | Seat table 6. Add **order B** (3 Garlic Naan, 2 Masala Chai). Send it. Make the bill. | Subtotal ₹375.00, service charge ₹37.50, GST ₹20.64, round off −₹0.14, **To pay ₹433**. |
| C-48 | Choose Cash and enter ₹400. | It says the cash is less than the bill and shows ₹33 still to pay. It does not settle. |
| C-49 | Change the cash to exactly ₹433 and confirm. | Settled, with nothing to give back. Tell your AI the cash line. |
| C-50 | Seat table 5, send 1 Masala Chai and make the bill. Before paying, use "Add guest" and enter a test phone number and name. Pay by UPI. | "Guest added." The guest's name shows on the bill. Removing and adding them again works. The bill settles. |

## 7. Table changes

| Step | Do this | Check |
|---|---|---|
| C-51 | Seat table 1 with 2 guests and send 2 Masala Chai. Then **move the table** to free table 8. | Everything moves to table 8. Table 1 becomes free (or Cleaning). The running total is unchanged. |
| C-52 | With table 8 seated, **join** it with free table 7. | Both tables show as seated, as one party with one bill. Un-join table 7 again: it is released. |
| C-53 | Seat table 1 again (mark it clean first if it shows Cleaning) and send 1 Filter Coffee. **Move items**: move 1 Masala Chai from table 8 to table 1. | The chai leaves table 8's total and appears on table 1's. Nothing is lost or doubled. |
| C-54 | Seat table R2 (Rooftop) with 2 guests. Add **order F** (1 Butter Chicken, 2 Garlic Naan, 2 Mango Lassi). Send. Make the bill. | Rooftop prices are used: Butter Chicken ₹400, Garlic Naan ₹95, Mango Lassi ₹145. **To pay ₹1,016** (not ₹912). |
| C-55 | Settle tables 1, 8 and R2 by UPI (mark paid). | All three close. |
| C-56 | Seat a table, send 2 different dishes, make the bill, then **split by items**: one dish on each bill. | Two bills. Every dish is on exactly one of them. Each bill has its own number and its own service charge, GST and round off. Together the two totals are within ₹1 of what one bill would have been. Pay both by UPI. |

## 8. Orders from guests' phones

Needs a teammate playing the customer (script 5) and one playing the waiter (script 3).

| Step | Do this | Check |
|---|---|---|
| C-57 | Ask the customer to place an order from their phone at a table. Watch the floor and the side menu. | The table shows that a QR order is waiting, and Guest orders shows a count. |
| C-58 | Open **Guest orders**. Read the waiting order. | It shows the table, the dishes, any notes and how long it has waited. |
| C-59 | Accept it. | "Sent to the kitchen." It leaves the list and the kitchen display shows it. |
| C-60 | Ask the customer to order again. This time **decline** it and pick a reason. | You must pick a reason first. The customer's phone shows it was declined, with your reason. Nothing reaches the kitchen. |
| C-61 | Ask the customer to order once more. Wait 2 minutes without accepting. | The table on the floor shows "Order waiting" with the minutes. It clears when you accept. |

## 9. After the sale

| Step | Do this | Check |
|---|---|---|
| C-62 | Open **Today's bills**. | The counts and amounts at the top (All, Paid, Waiting to pay, Open orders, Void) match what you did today. |
| C-63 | Find the order A bill by its number, then by table. Open it. | Same dishes, amounts and bill number as when you settled it: ₹785. |
| C-64 | Reprint that bill's receipt. | The till says the receipt went to the printer (or clearly that it did not). The bill number and amounts do not change. |
| C-65 | Try to change, void or delete that paid bill. | You cannot. At most it offers a credit note, and that needs a manager. |
| C-66 | Look at every bill number you made today. | No number appears twice. Each looks like `ABC-2627-000042`: letters and digits with dashes, 16 characters or fewer. |
| C-67 | Seat a table, send 1 Masala Chai, then try "Void bill" or "Record walk-out" from "Discount or void". | It needs a manager. Ask a manager to cancel the order, or pay it. |

## 10. The cash drawer and the end of the day

| Step | Do this | Check |
|---|---|---|
| C-68 | Cash drawer → Cash in or out → **Pay in** ₹200. Pick a reason. | "Cash movement recorded." Expected in drawer goes up by ₹200. Tell your AI: *"Cash: pay in 200."* |
| C-69 | **Pay out** ₹150 for a small expense (e.g. milk). Pick a reason and an expense head. | Recorded. Expected goes down by ₹150. Tell your AI. |
| C-70 | Try a pay out with no reason, with ₹0, and with more than the drawer holds. | Each is refused clearly, or handled sensibly. Nothing is recorded. |
| C-71 | **Safe drop** ₹1,000. | Recorded. Expected goes down by ₹1,000. Tell your AI. |
| C-72 | Read Drawer activity. | Your pay in, pay out and safe drop are listed, newest first, with the right amounts. |
| C-73 | Read "Today so far · X report". | Sales, bills and the split by payment method match what you sold. Card and UPI sales are not counted as cash. |
| C-74 | Ask your AI: *"What should the drawer hold?"* Compare with Expected in drawer. | They match to the rupee. If you did every cash step in this script exactly once and nobody else took cash, both are **₹5,113**. |
| C-75 | Close the drawer. Count each note and coin; enter exactly the expected amount. | It says the count matches. "Drawer closed. It balances." |
| C-76 | Ask the manager to open the drawer again with a float of ₹1,000 and close it with a count of ₹400 (₹600 short). | It shows Short ₹600 and asks for a manager's PIN, because the difference is above ₹500. With the PIN it closes and records who approved. |
| C-77 | With the drawer closed, try to take a cash payment. | Refused: the drawer is closed. |

## 11. Mistakes a real cashier makes

| Step | Do this | Check |
|---|---|---|
| C-78 | Tap **Settle** twice very quickly on a table bill (drawer open again, pay by UPI). | One invoice, one payment. |
| C-79 | Close the till app in the middle of an order on a table, then start it again and unlock. | The table, its sent dishes and its total are all still there. |
| C-80 | Type strange amounts in "Cash given": 0, letters, 10.555, 1,00,000. | Clear messages. No wrong totals or change. |
| C-81 | Open a back-office item in the side menu (e.g. Menu) with your cashier PIN. | You see only what a cashier may see, or a clear "no access" message. |
| C-82 | Add 30 different dishes to one takeaway ticket, with quantities above 10. | The ticket scrolls and stays readable. The total is right and written the Indian way (e.g. ₹1,00,000). Clear it. |

**Done?** Tell your AI: "Finished cashier script." Mention any steps you skipped or that were blocked.
