# Script 5: Customer ordering and table booking

**You are:** a guest sitting at table 3, ordering from your own phone.
**You need:** your own phone on mobile data (not the restaurant's Wi-Fi), the printed QR for table 3, the booking link from the tech lead, and [the test restaurant page](../TEST-RESTAURANT.md).
**Teammates:** a waiter (script 3, steps W-21 to W-31) for sections 2 to 4. A second customer with their own phone for section 5.
**Time:** about 1.5 hours.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, say "G-xx not there". If you can't do a step, say "G-xx blocked".

**Never pay real money** unless the tech lead tells you to.

## 1. Look at the menu

No waiter is needed yet. Anyone can look.

| Step | Do this | Check |
|---|---|---|
| G-01 | Scan table 3's QR with your phone camera. | The menu opens in about 2 seconds, with the restaurant's name and "table 3". You did not have to install anything or sign in. |
| G-02 | Browse every category. | All seven categories and their dishes load, with photos and prices that match the price list (Main Hall prices). |
| G-03 | Use search and the vegetarian filter. | Search finds dishes by part of the name. The filter hides non-veg dishes. |
| G-04 | Ask the waiter to mark Rasmalai sold out (W-19), then look at it. | It is shown as sold out and cannot be added. When the waiter brings it back, you can add it again. |
| G-05 | Open Masala Dosa. Add Cheese. Set the quantity to 2. Add a note: "less spicy". | The price shows ₹150 + ₹40 for each. The note is kept. |
| G-06 | If the owner made `TEST Lemon Soda` with a choice you must make (O-16), try to add it without choosing. | It stops you and shows what is required. With the choice made, it adds. |
| G-07 | Open the cart. Change a quantity, remove a dish, then clear the cart. | The total updates correctly each time. Clearing asks you to confirm. |

## 2. Get permission to order

| Step | Do this | Check |
|---|---|---|
| G-08 | Put 1 Masala Chai in the cart and try to place the order before any waiter has paired you. | You cannot. You are asked to have your server start the order. Nothing reaches the restaurant. |
| G-09 | Tap "Ready to order". | You are asked to scan your server's code, or told that your server has been told. It never places an order by itself. |
| G-10 | The waiter shows their pairing code (W-21). Scan it from the app's own scanner. | You are connected to table 3. The screen names your server. |
| G-11 | If your camera does not work, type the code, or the table PIN the waiter reads out. Type a wrong PIN once first. | The wrong PIN is refused clearly and tells you how many tries are left. The right one connects you. (Don't try more than twice: five wrong PINs lock the table's PIN.) |
| G-12 | If asked for your phone number, enter it and the code you receive. Enter a wrong code once. | The code arrives within about a minute. The wrong code is refused. |

## 3. Order, round after round

This is **order G** on the test restaurant page.

| Step | Do this | Check |
|---|---|---|
| G-13 | Clear the cart. Place round 1: 2 Masala Dosa, 2 Filter Coffee. | You see it was sent to your server and is waiting. It is **not** shown as being cooked yet. |
| G-14 | Ask the waiter to accept it (W-26). | Within a few seconds your screen shows the round as accepted. |
| G-15 | Tap Place order twice very quickly on a second order of 1 Gulab Jamun. | One order is sent, not two. |
| G-16 | Ask the waiter to reject that order with a reason (W-27). | Your screen shows it was not accepted, with the waiter's reason. |
| G-17 | Place round 2: 1 Rasmalai. You do not scan anything again. | It is sent without pairing again. After the waiter accepts it (W-28), it shows as accepted. |
| G-18 | Open My orders. | Both accepted rounds are listed, and the running total covers only accepted rounds: ₹590 before the service charge and GST. The rejected Gulab Jamun is not counted. |
| G-19 | Tap Call server. Then Ask for water. Then Ask for the bill. Then Ready to order, if it is shown. | Each shows as sent, then "On their way" when the waiter picks it up (W-29, W-30). Asking for the same thing again says you already asked. |
| G-20 | Ask the waiter to prepare the bill. Look for a way to pay on your phone. | The table shows the bill is being settled. There is no pay button: you are told your server will take payment at the table. The bill is **₹681**. |

## 4. Real-life problems

| Step | Do this | Check |
|---|---|---|
| G-21 | Before the bill is paid, refresh the page. Then close the browser and scan table 3's QR again. | You are still connected to your table and your orders are still there. You did not need the waiter again. |
| G-22 | Lock your phone for 5 minutes, then come back. | The page still works. Your orders are right. |
| G-23 | Switch between Wi-Fi and mobile data, or go to a weak-signal spot, and place an order. | It either goes once, or you get a clear message. Never a spinner for more than about 5 seconds. Never a double order. |
| G-24 | After the waiter has taken payment and the table is closed, try to order again. | You cannot. A new visit needs the waiter to pair you again. |
| G-25 | Scan the QR of a **different** table (table 4). | You see the menu, but none of table 3's orders. You cannot order on table 4 without that table's waiter pairing you. |
| G-26 | Open the page in a private (incognito) window using table 3's link. | You see the menu only. You are not connected to any table. |

## 5. Two guests at one table

Needs a second customer with their own phone. Start a new visit on table 3 with the waiter.

| Step | Do this | Check |
|---|---|---|
| G-27 | You pair and order 1 Masala Chai. The second customer scans table 3's QR and tries to order without pairing. | They can browse but not order. |
| G-28 | Use "Invite your table" to share the table, or have the waiter show the code to the second customer. | The second customer joins the same table. |
| G-29 | The second customer looks at My orders. | They see your Masala Chai and the same running total as you. |
| G-30 | Both of you place a different dish at the same moment. | Both orders reach the waiter, once each. After the waiter accepts both, both phones show the same list and the same total. |
| G-31 | Ask the waiter to prepare the bill. A third phone now tries to join. | It is refused: the bill is in progress. The two of you can still add a dessert. |
| G-32 | Ask the waiter to unpair the devices (W-31). | Neither of you can order any more. |

## 6. Takeaway from a QR

Only if the tech lead gave you a takeaway (counter) QR or link. Otherwise say "G-33 to G-35 not there".

| Step | Do this | Check |
|---|---|---|
| G-33 | Open the takeaway link. Add **order T1** (1 Chicken Biryani, 1 Sweet Lassi). | No waiter is needed. The total is **₹483**, with ₹10 packaging and no service charge. |
| G-34 | Pay with the test payment the tech lead gave you. | You see Paid and your collection number. The kitchen gets the order only after the payment went through. |
| G-35 | Start another takeaway and cancel the payment half-way. | You are told the payment did not go through. No order reaches the kitchen. You are not charged. |

## 7. Book a table

| Step | Do this | Check |
|---|---|---|
| G-36 | Open the booking link. Choose tomorrow, 4 people, and look at the available times. | Times are offered in 30-minute steps, only while the restaurant is open. |
| G-37 | Book 8:00 pm with your name and phone number. | You see either "Your table is confirmed" or that the request was sent and the restaurant will confirm. Any SMS arrives. |
| G-38 | Try to book: a date in the past, 0 people, 13 people, a phone number with letters, no name. | Each is stopped with a clear message. Nothing is booked. |
| G-39 | Tap the Book button twice very quickly on a second booking. | One booking is made, not two. |
| G-40 | Ask the owner or manager to look in Reservations. | Your booking is there once, with the right date, time, party size, name and phone. |

**Done?** Tell your AI: "Finished customer script." Mention any steps you skipped or that were blocked.
