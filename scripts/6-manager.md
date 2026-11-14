# Script 6: Manager

**You are:** Meera, the outlet manager. Staff call you when something needs your approval, when a bill has to be corrected, and at the end of the day.
**You need:** your own till PIN, the manager login for the dashboard on a laptop, and [the test restaurant page](../TEST-RESTAURANT.md).
**Teammates:** a cashier (script 2) for sections 1 and 2, and a waiter (script 3) for M-07. Do section 5 at the end of a testing day.
**Time:** about 2 hours.

Do each step in order. **Check** says what should happen. If it doesn't, screenshot and tell your AI the step number. If an option isn't on your screen, say "M-xx not there". If you can't do a step, say "M-xx blocked".

**Cash sheet.** When a refund is paid in cash from the drawer, tell your AI, e.g. *"Cash: refund 115.50 from drawer."*

## 1. Approvals at the till

The cashier stays signed in. You only type your PIN when the till asks for a manager.

| Step | Do this | Check |
|---|---|---|
| M-01 | Ask the cashier to seat table 8, send 2 Tandoori Chicken (Full), make the bill and try a flat discount of ₹600. When the till asks for a manager, type a wrong PIN. | Refused. The discount is not applied. |
| M-02 | Type your own PIN. | The ₹600 discount is applied once. The till stays signed in as the cashier, not as you. |
| M-03 | The cashier tries a second discount on the same bill straight after, without you. | The till asks for a manager again. Your approval covered one action only. Cancel it. |
| M-04 | Ask the cashier to type their own PIN in the manager box. | Refused: a cashier cannot approve. Pay table 8 by Card. |
| M-05 | The cashier seats table 7, sends 1 Tandoori Chicken (Full) and 1 Masala Chai, then cancels the Tandoori Chicken (₹580). | The till asks for a reason and for your PIN. With it, the dish is cancelled and the kitchen is told. |
| M-06 | The cashier cancels the rest of that order. | It needs a reason and your PIN. The table's total drops to nothing and the kitchen is told. |
| M-07 | The waiter cancels a sent dish from the waiter app (W-33). Type your PIN on the waiter's phone. | The dish is cancelled. Without your PIN, the waiter cannot do it. |
| M-08 | The cashier closes a drawer that is ₹600 short (C-76). | The till shows the difference and asks for your PIN. With it the drawer closes, and your name is recorded as the approver. |

## 2. Correcting bills

| Step | Do this | Check |
|---|---|---|
| M-09 | A table has an unpaid bill and the guests have gone (the cashier seats a table, sends 1 Masala Dosa and makes the bill). Unlock the till with your PIN. Open "Discount or void" and record a walk-out, with a reason. | "Walk-out recorded. The table is closed." The bill shows as void, not as a sale. |
| M-10 | On another unpaid bill, use "Void bill" with a reason. | "Bill voided." A reason is required. The dishes do not come back onto the table as unbilled. |
| M-11 | Open Today's bills. Find the takeaway bill for **order T1** (₹483, paid in cash). Issue a credit note for the Sweet Lassi only. | You pick the dish and quantity. The refund total is **₹115.50**. A reason is required. |
| M-12 | Refund it as cash from the drawer. | The credit note gets its own number. The drawer's expected cash drops by ₹115.50. Tell your AI the cash line. |
| M-13 | Open the original T1 bill again. | It is unchanged: same number, same ₹483. The credit note is shown against it. |
| M-14 | Try a second credit note on T1 for more than what is left (e.g. 2 Sweet Lassi, or the biryani twice). | Refused. Credit notes can never add up to more than the bill. |
| M-15 | Issue a credit note on a bill that was paid by the till's UPI QR, and send the refund back to UPI. | The till says the refund was initiated (not "refunded"). No cash leaves the drawer. In the dashboard, the bill later shows the refund and its status. |
| M-16 | Lock the till. Ask the cashier to unlock it and try to issue a credit note or void a bill. | The cashier cannot. It needs a manager. |

## 3. Running the floor

| Step | Do this | Check |
|---|---|---|
| M-17 | A guest's phone order is waiting on a waiter's table and the waiter is busy. Open Guest orders on the till and accept it yourself. | It goes to the kitchen. The waiting flag on the table clears. |
| M-18 | Wait until a guest order is more than 90 seconds old without anyone accepting it. | You are alerted that an order is waiting, with the table. The alert stops once it is accepted or declined. |
| M-19 | On the floor, seat a table that shows Cleaning or Paid without waiting. | The till asks you to confirm ("Seat anyway") and for a reason. The table opens. |
| M-20 | In the till's manager area, open Staff. Pick a `TEST` staff member and revoke their access now. | "Access revoked." Their PIN is refused at once on this till, and their waiter app stops working at their next action. Ask the owner to restore them afterwards. |
| M-21 | In the dashboard, open Staff & Access. Set a new till PIN for a `TEST` staff member. | The new PIN works on the till within a minute or two. The old one does not. |
| M-22 | In the dashboard, open Staff & Management. Approve the waiter's leave request (W-60). Correct one attendance entry, with a reason. | Both are saved. The correction shows who made it; the original punch is still visible. |
| M-23 | Open Reservations. Find tomorrow's 8 pm booking for 4 (G-37). Change it to 8:30 pm. Add a walk-in party to the waitlist. | Both save and stay after a refresh. |

## 4. The dashboard's POS page (when you are away from the till)

Use a laptop browser, signed in to the dashboard as the manager. The till must be on.

| Step | Do this | Check |
|---|---|---|
| M-24 | Open POS in the dashboard. | You see the same floor and tables as the till. |
| M-25 | Open a free table, add 1 Filter Coffee and send it. | The kitchen display shows it. The till's floor shows the table as seated. |
| M-26 | Make the bill and try to pay in **cash**. | Cash is refused with a clear message that cash is taken on the till. Card and UPI work. Pay by Card. |
| M-27 | Ask the tech team to close the till app. Try to add a round to a table from the browser. | You are told clearly that the till cannot be reached. Nothing is ordered. When the till is back, it works again. |
| M-28 | Leave the POS page untouched for 6 minutes. | You are signed out of it, as the till would lock. |

## 5. Closing the day

Do this last, when everyone has finished for the day.

| Step | Do this | Check |
|---|---|---|
| M-29 | Leave one table still seated with an unpaid order. On the till, open Cash drawer and look at the day-end section. | It lists what is stopping the day from closing: the open table, any unpaid bill, any open drawer, any guest order still waiting. |
| M-30 | Carry that table forward to tomorrow, with a reason. | "Session carried forward." It no longer blocks the day. A reason is required. |
| M-31 | Make sure every other table is paid or voided. Ask the cashier to close the drawer (C-75). | Nothing is left blocking. |
| M-32 | Print the Z report for the day. | It prints (or the till clearly says it could not). Its figures do not change if you print it again. |
| M-33 | Read the X or Z figures on the screen. Ask your AI: *"What were today's cash sales, and what should the drawer hold?"* | Sales by cash, card and UPI match the testers' sheets. Voids, walk-outs, discounts and the credit note each show as their own figure. The carried-forward table is listed and its amount is not in today's sales. |
| M-34 | Next morning, unlock the till. | The carried-forward table is still seated with its order. Settle it: the sale counts for the new day. |

## 6. Checking the day in the dashboard

| Step | Do this | Check |
|---|---|---|
| M-35 | Open Orders & Billing → Bills. Search for the order A bill by its number, then filter by date, by amount and by payment method. | Each search finds the right bills, including bills from earlier days. |
| M-36 | Open the order D bill, then the T3 bill. | Order D: same dishes and ₹3,107 as on the till, with both payments (₹2,000 cash, ₹1,107 UPI). T3: the slip number and approval code the cashier typed (C-17) are shown. |
| M-37 | Open Credit notes. | The T1 credit note is listed with ₹115.50, its reason, who issued it, and the bill it belongs to. |
| M-38 | Open Shifts. Open today's drawer. | It shows the float, every pay in, pay out and safe drop, expected and counted cash, the difference, and who approved a difference above ₹500. |
| M-39 | Open Day end. | Today's totals match the Z report from the till. Any UPI payment that reached no bill, or a bill paid twice, is listed for you to refund. |
| M-40 | Open Audit. Find the ₹600 discount, the walk-out and the credit note. | Each shows what was done, when, who did it and who approved it. |

**Done?** Tell your AI: "Finished manager script." Mention any steps you skipped or that were blocked.
