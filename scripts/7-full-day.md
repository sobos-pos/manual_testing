# Script 7: A full day of service

The whole team runs one day at the test restaurant together, from opening to closing. It ends with a check that every rupee is accounted for.

**Run it last,** after everyone has finished their own script. **Run it on a day when nobody does any other testing on this outlet,** and start with a clean day (`SETUP.md` section 6). Then the day's figures must match the table at the end exactly.

**Time:** about 3 hours.

## The team

| Role | Who | Uses |
|---|---|---|
| **Owner** | Rohan | Dashboard on a laptop |
| **Manager** | Meera | Till PIN, dashboard |
| **Cashier** | Priya | Till |
| **Waiter** | Wasim | Waiter app |
| **Kitchen** | Farhan | Kitchen display |
| **Guest 1, Guest 2** | Two testers | Their own phones |
| **Tech lead** | | Cuts and restores the internet in scene 8 |

Each person tells their own AI the step number if something goes wrong. The cashier, the waiter and the manager tell their AI every cash line. One person reads the steps aloud.

## Scene 1: Opening

| Step | Who | Do this | Check |
|---|---|---|---|
| D-01 | Waiter, Kitchen | Sign in and clock in. | Both show as on shift, with the right time. |
| D-02 | Cashier | Unlock the till. Open the cash drawer with a ₹2,000 float. | Expected in drawer: ₹2,000. *Cash: float 2000.* |
| D-03 | Kitchen | Open the kitchen display. | Empty and connected. |
| D-04 | Owner | Open the dashboard: home, Node & Devices and Staff attendance. | The till is online. No table is open. Today's sales are zero. The clock-ins are listed. |

## Scene 2: The takeaway rush

| Step | Who | Do this | Check |
|---|---|---|---|
| D-05 | Cashier | Sell **T1** for `TEST Ravi`: cash, ₹500 given. | To pay ₹483, change ₹17. A pickup token is shown. *Cash: T1 483.* |
| D-06 | Waiter | Sell **T2** from the waiter app for `TEST Anita`: UPI. | To pay ₹284. It gets the next token and its own bill number. |
| D-07 | Cashier | Sell **T3** for `TEST Office`: card, with a slip number. | To pay ₹2,783. |
| D-08 | Kitchen | Watch the three tickets. Bump each when "cooked". | Three takeaway tickets, in the order they were sold, each with the customer's name or token. None missing, none doubled. |

## Scene 3: A family of six

| Step | Who | Do this | Check |
|---|---|---|---|
| D-09 | Waiter | Seat table 7 with 6 guests and join table 8 to it. | Both tables show as one party, on the phone and on the till. |
| D-10 | Waiter | Send round 1: 1 Paneer Tikka, 1 Chicken 65, 2 Butter Chicken (one Mild with the note "for a child"), 1 Dal Makhani, 6 Butter Naan, 2 Jeera Rice. | Kitchen: Paneer Tikka and the naan at Tandoor, the rest at Main Kitchen, the note visible. |
| D-11 | Waiter | Send round 2: 3 Gulab Jamun, and 1 Chicken 65 added by mistake. Then cancel the extra Chicken 65. | The cancel needs a reason and the **manager's PIN** on the phone. Kitchen: round 2 is marked NEW; the cancelled dish is struck through. |
| D-12 | Kitchen, Waiter | Kitchen bumps both rounds. Waiter marks them served. | The waiter is told the food is ready each time. |
| D-13 | Cashier | On the till, make the bill for tables 7 and 8. | One bill for **order D**: Subtotal ₹2,690.00, service charge ₹269.00, GST ₹147.96, round off +₹0.04, **To pay ₹3,107**. |
| D-14 | Cashier | Split the payment equally between 3 guests. Take UPI, Card, UPI. | Shares of ₹1,035.67, ₹1,035.67 and ₹1,035.66. One bill, one invoice number, three payments. Both tables show Paid. |

## Scene 4: Guests order from their phones

| Step | Who | Do this | Check |
|---|---|---|---|
| D-15 | Waiter, Guest 1, Guest 2 | Waiter seats table 3 and shows the pairing code. Both guests scan table 3's QR, then pair. | The waiter's app shows 2 devices paired to table 3. Each guest sees the waiter's name. |
| D-16 | Guest 1, Waiter | Guest 1 orders 2 Masala Dosa and 2 Filter Coffee. The waiter accepts. | Nothing reaches the kitchen until the waiter accepts. Then one ticket appears. Guest 2's phone shows the same order. |
| D-17 | Guest 2 | Order 1 Rasmalai. The waiter does **not** accept it for 2 minutes. | After 90 seconds: the waiter's floor and the till's floor both show "Order waiting" on table 3, and the manager is alerted. |
| D-18 | Manager | Accept the waiting order from Guest orders on the till. | It goes to the kitchen. The waiting flag clears everywhere. Both guests see it as accepted. |
| D-19 | Guest 1, Waiter | Guest 1 asks for water, then for the bill. | The waiter gets each request within a few seconds, on table 3. |
| D-20 | Waiter | Prepare table 3's bill and take a card payment. | **Order G: To pay ₹681.** After payment, neither guest can order any more. |

## Scene 5: A party moves upstairs

| Step | Who | Do this | Check |
|---|---|---|---|
| D-21 | Waiter | Seat table 4 with 2 guests. Send 1 Butter Chicken and 2 Butter Naan. | Running total at Main Hall prices: ₹500 before charges. |
| D-22 | Waiter | Move the table to R3 on the Rooftop. Then send 2 Mango Lassi. | The lassis are ₹145 each (Rooftop price). The Butter Chicken stays ₹360 and the naan ₹70. |
| D-23 | Cashier | Make the bill for R3 and take UPI. | **Order H: To pay ₹912.** Table 4 was released when the party moved. |

## Scene 6: The kitchen runs out

| Step | Who | Do this | Check |
|---|---|---|---|
| D-24 | Guest 1 | Scan table 5's QR and put a Paneer Tikka in the cart. | It is in the cart. |
| D-25 | Waiter | Mark Paneer Tikka sold out in the waiter app. | Within a few seconds it shows sold out on the till, the waiter app and the guest menu. The owner's dashboard shows it too. |
| D-26 | Guest 1, Cashier | Guest 1 looks at the cart. The cashier tries to add Paneer Tikka on the till. | Neither can order it. The guest is told clearly. |
| D-27 | Waiter | Bring Paneer Tikka back. | It can be ordered again everywhere. |

## Scene 7: Two awkward guests

| Step | Who | Do this | Check |
|---|---|---|---|
| D-28 | Cashier | Seat table 5. Send **order A**. Make the bill (₹785). The guest refuses the service charge: waive it with a reason. Take ₹1,000 cash. | No manager needed. **To pay ₹714**, change ₹286. *Cash: Order A 714.* |
| D-29 | Manager | The takeaway guest from D-05 comes back: the lassi was sour. Issue a credit note on the T1 bill for the Sweet Lassi, refunded in cash. | Refund **₹115.50**. The T1 bill itself is unchanged. *Cash: refund 115.50.* |
| D-30 | Cashier, Manager | Seat table 6. Send 2 Masala Chai. Make the bill (₹139). The guests leave without paying. The manager records a walk-out. | The table closes. The bill shows as void, not as a sale. |

## Scene 8: The internet goes down at the busiest time

The tech lead cuts the internet but leaves the restaurant's own network on. Keep it off for 20 minutes.

| Step | Who | Do this | Check |
|---|---|---|---|
| D-31 | Tech lead | Cut the internet. Tell everyone. | — |
| D-32 | Cashier | Look at the till. | It says it is offline and that sales stay on this till until it reconnects. Billing still opens. |
| D-33 | Cashier | Seat table 1. Send **order B**. Make the bill. Open the payment screen. | **To pay ₹433.** Cash, Card and UPI (marked by hand) are offered. Any online QR is greyed out with "Needs internet". Take ₹433 cash. *Cash: Order B 433.* |
| D-34 | Waiter | Seat table 2. Send **order C** from the waiter app. Prepare the bill. Take a card payment. | The app works as normal on the restaurant's network. **To pay ₹1,086.** |
| D-35 | Kitchen | Watch the display. | Both orders arrive as fast as before. |
| D-36 | Guest 2 | Scan a table QR and try to order. | A clear message says ordering from the phone is not available and the waiter will take the order. No spinner for more than about 5 seconds. |
| D-37 | Cashier | Open a back-office item on the till (e.g. Menu). | It says the page needs the internet, and that selling still works. |
| D-38 | Owner | Look at the dashboard from a phone on mobile data. | The till shows as offline. The two offline bills are not there yet. |
| D-39 | Tech lead | Restore the internet. | — |
| D-40 | Owner, Cashier | Wait up to 5 minutes. Compare Today's bills on the till with Bills in the dashboard. | The till says it is online and everything has been sent. Order B and order C each appear in the dashboard **once**, with the same bill numbers and amounts as on the till. No bill number is repeated. |
| D-41 | Guest 2 | Try ordering from the phone again. | It works again. |

## Scene 9: A booking arrives

| Step | Who | Do this | Check |
|---|---|---|---|
| D-42 | Guest 1 | In the morning, book a table for tonight for 4 from the booking page. | Confirmed, or request sent. |
| D-43 | Manager | When the party "arrives", find the booking in Reservations and seat it at a table. | The booking shows as seated. The table shows as seated on the till and the waiter app. If the table showed Reserved beforehand, say so; if not, see OQ-2 in [known limits](../KNOWN-LIMITS.md). |
| D-44 | Waiter | Send 1 Filter Coffee to that table. Leave it unpaid. | It reaches the kitchen. |

## Scene 10: Closing

| Step | Who | Do this | Check |
|---|---|---|---|
| D-45 | Manager | On the till, look at what is stopping the day from closing. | The booking's table (1 Filter Coffee, unpaid) is listed. Nothing else. |
| D-46 | Manager | Carry that table forward to tomorrow, with a reason. | It no longer blocks the day. |
| D-47 | Cashier | Read the X report and Expected in drawer. Ask your AI what the drawer should hold. | Expected in drawer is **₹3,514.50**: ₹2,000 float + ₹1,630 cash sales − ₹115.50 refund. Your AI's figure agrees. |
| D-48 | Cashier | Count the play money. Close the drawer with the real count. | If the count is ₹3,514.50, it balances. If the team made a cash mistake, the difference shown is exactly that mistake. |
| D-49 | Manager | Print the Z report. | It closes the day. Its figures match the table below. |
| D-50 | Waiter, Kitchen | Clock out. | The times are right. |

## The day must add up to this

Compare the Z report, the dashboard (Day end, and the sales summary in Analytics) and your AI's totals. All three must agree with this table.

| | Amount |
|---|---|
| Paid bills | 9 |
| Total collected | **₹10,483.00** |
| of which Cash | ₹1,630.00 (T1, order A, order B) |
| of which UPI | ₹3,267.33 (T2, two shares of order D, order H) |
| of which Card | ₹5,585.67 (T3, one share of order D, order G, order C) |
| Voided bills | 1 (the walk-out, ₹139) |
| Credit notes | 1 (₹115.50, refunded in cash) |
| Service charge waived | 1 (₹68.00 plus its GST ₹3.40) |
| Carried forward | 1 table (1 Filter Coffee, not in today's sales) |
| Expected cash in the drawer | **₹3,514.50** |

## The next morning

| Step | Who | Do this | Check |
|---|---|---|---|
| D-51 | Owner | Open the dashboard. Look at yesterday in Day end, Shifts and the sales summary. | The same figures as the table above. The drawer shows its float, its count, and any difference with who approved it. |
| D-52 | Owner | Open Audit. Find the cancelled Chicken 65, the waived service charge, the credit note, the walk-out and the carried-forward table. | Each is there with who did it, who approved it, when and why. |
| D-53 | Cashier | Unlock the till. | The carried-forward table is still seated with its Filter Coffee. Yesterday's bills are not in Today's bills. |
| D-54 | Cashier | Open the drawer for the new day. Settle the carried-forward table in cash. | **To pay ₹81.** The sale counts for today, not yesterday. Yesterday's Z does not change. |

**Done?** Each person tells their own AI: "Finished full-day script, steps … passed."
