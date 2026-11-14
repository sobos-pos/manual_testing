# Script 4: Kitchen

**You are:** Farhan, a cook. You work from the kitchen display: orders arrive as tickets, and you mark them ready.
**You need:** the kitchen display (it opens from the till: Kitchen → Open kitchen display; the tech team may put it on a second screen), your till PIN, and [the test restaurant page](../TEST-RESTAURANT.md).
**Teammates:** a cashier (script 2) or a waiter (script 3) to send you orders. Agree which orders they send and when.
**Time:** about 1 hour, of which 20 minutes is waiting for one ticket to turn late.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, say "K-xx not there". If you can't do a step, say "K-xx blocked".

## 1. Tickets arrive

| Step | Do this | Check |
|---|---|---|
| K-01 | Open the kitchen display. | It opens and shows it is connected. With no orders, it says so clearly instead of showing a blank screen. |
| K-02 | Ask the cashier to send **order A** from table 4 (1 Butter Chicken, 2 Butter Naan, 1 Jeera Rice). | The ticket appears within about a second of the cashier sending it. You do not need to refresh. |
| K-03 | Read the ticket. | It shows table 4, each dish with its quantity, and a timer counting up. It shows no prices. |
| K-04 | Ask the waiter to send a Butter Chicken with spice level "Hot" and the note "less oil". | The spice level and the note are on the ticket, easy to see. |
| K-05 | Ask the cashier to sell a takeaway (**order T1**). | The ticket says Takeaway, with the customer's name or the pickup token, not a table. |
| K-06 | Ask for a dish with an extra (Masala Dosa with Cheese). | The extra is listed under its dish. |

## 2. Stations

| Step | Do this | Check |
|---|---|---|
| K-07 | Look at the station filter. | Main Kitchen, Tandoor and Beverage Bar can be picked. |
| K-08 | Filter to **Tandoor**. | From order A you see only the Butter Naan. Paneer Tikka, Tandoori Chicken and all breads come here. |
| K-09 | Filter to **Beverage Bar**. Ask for 2 Mango Lassi and 1 Masala Chai. | Drinks appear here and not at Main Kitchen. |
| K-10 | Filter to **Main Kitchen**, then back to all stations. | Curries, rice, starters (except tandoor dishes) and desserts are at Main Kitchen. With all stations chosen, nothing is missing. |

## 3. Changes to an order

| Step | Do this | Check |
|---|---|---|
| K-11 | Ask the cashier to add a second round to table 4 (1 Gulab Jamun). | The new dish is marked **NEW**. The first round is not sent again. |
| K-12 | Ask the cashier to send 3 Butter Naan on a new table, then cancel one of them. | The ticket shows the change: **3 → 2**. |
| K-13 | Ask the cashier to cancel a whole dish that was sent. | The dish is struck through on the ticket, and the display makes a sound. |
| K-14 | Ask the cashier to add a kitchen note to a sent dish ("no onion"). | The note appears on the ticket. |

## 4. Timers

| Step | Do this | Check |
|---|---|---|
| K-15 | Leave one ticket untouched. Note the time it arrived. Carry on with other steps. | At 15 minutes it is marked **Aging**. |
| K-16 | Keep waiting on that ticket. | At 20 minutes it is marked **Late**, the display plays a sound once, and a "late" count shows at the top. |
| K-17 | Check the timer against a clock. | The minutes on the ticket match the real waiting time. |

## 5. Marking ready

| Step | Do this | Check |
|---|---|---|
| K-18 | Bump (mark ready) the order A ticket. | It shows as bumped and leaves the open tickets. The waiter's phone shows the order as ready to serve within a few seconds. |
| K-19 | Tap Bump twice very quickly on another ticket. | It is bumped once. No error. |
| K-20 | If you bump a ticket by mistake, bring it back, if there is a way, within a minute. | It returns to the open tickets with its timer still running. |
| K-21 | Ask the cashier to send 10 small orders one after another, as in a rush. | All 10 appear, in the order they were sent. None is missing or doubled. The display stays quick. |
| K-22 | Bump tickets on one station while another station's tickets for the same table are still open. | Only that station's ticket is cleared. The other station still sees its part. |

## 6. Things going wrong

| Step | Do this | Check |
|---|---|---|
| K-23 | Close the kitchen display window, then open it again from the till. | Every open ticket is back, with the right timers. |
| K-24 | Ask the tech team to lock the till, or open the display as someone who is not kitchen staff. | The display can be read but shows "Read only", and tickets cannot be bumped. |
| K-25 | Ask the tech team to cut the internet for 5 minutes (the local network stays on). Have the cashier send two orders. | Tickets keep arriving as normal. The kitchen does not depend on the internet. |
| K-26 | Look at the whole display from two metres away. | Table numbers, dishes and quantities can be read from where a cook stands. |

**Done?** Tell your AI: "Finished kitchen script." Mention any steps you skipped or that were blocked.
