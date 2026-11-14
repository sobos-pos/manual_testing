# Money and tax checklist

Work every figure out yourself before you look at the screen. The standard orders and their totals are on [the answer sheet](../TEST-RESTAURANT.md). **Any difference, even one paisa on a tax line, is a P0 bug.**

Check each figure in four places: the till's screen, the waiter app, the printed bill, and the dashboard's bill. All four must agree.

The rules, in the order they apply: subtotal → discount → service charge (table bills) or packaging (takeaway) → GST on each line and on each charge, every component rounded on its own, half up → round off to the nearest rupee → to pay.

## GST and rounding

| ID | Check | Pass when |
|---|---|---|
| MT-01 | **Order A** | CGST ₹18.70 and SGST ₹18.70 shown separately (₹17.00 on the dishes plus ₹1.70 on the service charge, each). To pay ₹785. |
| MT-02 | **Order B**, with 3 Garlic Naan as **one** line | Tax on the naan line is ₹6.38 + ₹6.38 (2.5% of ₹255 is ₹6.375, rounded half up, on each component). Total GST ₹20.64. To pay ₹433. |
| MT-03 | 3 Garlic Naan added as **three separate rounds** | Tax on them is ₹12.78, not ₹12.76: each line rounds on its own. This is by design. |
| MT-04 | **T2** | ₹283.50 before round off. Round off +₹0.50. To pay ₹284 (a half rounds up). |
| MT-05 | Round off line on every standard order | It is its own visible line, never hidden inside tax. It matches the answer sheet, including the minus sign. |
| MT-06 | A `TEST` dish with a different tax rate on the same bill as standard dishes | Each rate's tax is worked out on its own lines and shown. |
| MT-07 | Menu prices include GST (turn the setting on for this check, then **off**) | A ₹100 dish costs the guest exactly ₹100: base ₹95.24, CGST ₹2.38, SGST ₹2.38. Butter Chicken at ₹360: base ₹342.86, tax ₹8.57 + ₹8.57. |

## Charges

| ID | Check | Pass when |
|---|---|---|
| MT-08 | Service charge after a discount, **order E** with 10% off | Service charge ₹127.80 (10% of ₹1,278), not ₹142.00. To pay ₹1,476. If the charge stays at ₹142.00 (to pay ₹1,491), record it against open question OQ-1. |
| MT-09 | Service charge on takeaway | None. |
| MT-10 | Waive the service charge on order A as a **cashier** | No manager needed. A reason is required. The ₹68.00 and its ₹3.40 GST both go. To pay ₹714. The waiver is recorded with who and why, and counted on the Z report. |
| MT-11 | "Charge GST on the service charge" turned off (then back **on**) | Order A: GST ₹34.00, to pay ₹782. |
| MT-12 | Service charge set to 0 (then back to **10**) | Order A: to pay ₹714. No service charge line. |
| MT-13 | Packaging on takeaway | ₹10.00 once per bill, however many dishes, with ₹0.25 + ₹0.25 GST. None on table bills. |

## Discounts

| ID | Check | Pass when |
|---|---|---|
| MT-14 | 10% and a flat ₹142 on order E | Both give the same bill. The discount comes off before GST. Each line's share of a flat discount is in proportion to its price, and the shares add up to exactly ₹142.00. |
| MT-15 | A discount above ₹500 as a cashier (₹600 on 2 Tandoori Chicken, Full) | It needs a manager's PIN. After approval: service charge ₹56.00, GST ₹30.80, to pay ₹647. The bill records both the cashier and the manager. |
| MT-16 | A discount of exactly ₹500 | No manager needed. |
| MT-17 | A discount bigger than the bill, a percentage above 100, a negative discount | Refused. Never a negative bill. |
| MT-18 | A 100% discount, approved by a manager | To pay ₹0. No service charge or GST is added. The bill can be settled with no payment, and reports show it as a ₹0 sale with its discount. |
| MT-19 | Two discounts on one bill | They add up; the second does not silently replace the first. |

## Paying

| ID | Check | Pass when |
|---|---|---|
| MT-20 | Split **order D** equally between 3 | ₹1,035.67 + ₹1,035.67 + ₹1,035.66 = ₹3,107 exactly. Between 4: ₹776.75 each. |
| MT-21 | Split **order A** by items: Butter Chicken on one bill, the rest on another | Two full bills with their own numbers: ₹416 and ₹370. Before round off they are ₹415.80 and ₹369.60, which add up to the original ₹785.40. Every dish is on exactly one bill. |
| MT-22 | One bill paid by cash, card and UPI | The three amounts add up to the bill. The bill is settled only when fully covered. One invoice number. |
| MT-23 | Cash given less than the bill, equal to it, and more | Less: not settled, the rest shown as still to pay. Equal: no change. More: the right change. |
| MT-24 | A card or UPI amount larger than what is due | Refused, or capped at what is due. Change is only ever given for cash. |
| MT-25 | Part payment, then the till app is killed | After restart the first payment is still on the bill and only the rest is due. |
| MT-26 | "Ask for a tip" turned on (then **off**): a tip with a card payment, and with cash only | The card tip is recorded separately and is not in sales or GST. A tip on a cash-only payment is refused. A tip is never added to an online UPI QR amount. |

## Corrections

| ID | Check | Pass when |
|---|---|---|
| MT-27 | Void an unpaid bill, and record a walk-out | Each needs a reason; above ₹500 a manager's PIN. Neither counts as a sale. The Z report shows voids, with walk-outs as their own figure inside them. |
| MT-28 | Try to void or edit a **paid** bill | Not possible. A credit note is the only correction. |
| MT-29 | Credit note for the Sweet Lassi on **T1** | ₹115.50: ₹110.00 plus ₹2.75 + ₹2.75 GST. It has its own number (e.g. `KOR-CN2627-00001`). The original bill is unchanged and shows the credit note against it. |
| MT-30 | Credit notes that together exceed the bill | Refused. |
| MT-31 | Change a dish's price or tax rate in the dashboard, then credit-note a bill made before the change | The credit note reverses the old price and the old rate. |
| MT-32 | Reprint, and open in the dashboard, a bill made before a price change | Same amounts as the day it was made. |
| MT-33 | Refund in cash, and back to UPI | Cash: the drawer's expected cash drops by the refund. UPI: no cash leaves; the refund shows as initiated, then processed. |

## Bill numbers

| ID | Check | Pass when |
|---|---|---|
| MT-34 | The format | Outlet code, financial year, six digits, e.g. `KOR-2627-000042`. Only capital letters, digits, `-` and `/`. 16 characters or fewer. Credit notes: `KOR-CN2627-00042`. |
| MT-35 | Every bill number of the round, on the till and in the dashboard | **No number is ever repeated.** On one till the numbers only go up. |
| MT-36 | Gaps | A gap between two tills' numbers, or after a returned block, is by design. A gap inside one till's own run of numbers is a bug unless the dashboard explains it. |
| MT-37 | A split-by-items bill, a credit note, a takeaway and a table bill | Each gets its own number. A voided unpaid bill never used an invoice number. |
| MT-38 | Number series settings | A format that could exceed 16 characters is refused with the reason. The outlet's 3-character invoice code is locked once the outlet has a bill, and a code used by another outlet is refused. |

## The drawer and the day

| ID | Check | Pass when |
|---|---|---|
| MT-39 | Expected cash | Float + cash sales (after change) + pay ins − pay outs − safe drops − cash refunds. Card and UPI never move it. |
| MT-40 | Close the drawer ₹400 short, exactly ₹500 short, ₹600 short, and ₹600 over | ₹400 and ₹500: closes without a manager, with the difference recorded. ₹600 short or over: needs a manager's PIN, and records who approved. There is no "waiting for approval" state. |
| MT-41 | Z report | Sales equal the sum of the day's paid bills. Each payment method equals the sum of its payments. Tax equals the sum of the bills' tax lines. Voids, walk-outs, discounts, waivers and credit notes each have their own figure. |
| MT-42 | Try to run the Z with a drawer open, a table unpaid, or a guest order waiting | Refused, listing each thing that blocks it. There is no way to force it. |
| MT-43 | A Z report once made | It cannot be changed or run a second time for the same day. |
| MT-44 | Dashboard reports against bills | Gross, net, tax, charges, discounts and round off in Analytics equal the bills for the same dates. |

## Other

| ID | Check | Pass when |
|---|---|---|
| MT-45 | Rooftop prices: **order F** | ₹1,016, using ₹400, ₹95 and ₹145. The same dishes in the Main Hall: ₹912. |
| MT-46 | A table moved from Main Hall to Rooftop mid-meal: **order H** | Rounds sent before the move keep Main Hall prices; rounds after it use Rooftop prices. To pay ₹912. |
| MT-47 | A price changed in the dashboard while a table is open | Dishes already sent keep their price. Dishes added afterwards use the new price. |
| MT-48 | A very large order: 50 lines, above ₹1,00,000 | Totals are right. Amounts are written the Indian way. Nothing overflows on screen or paper. |
| MT-49 | Amounts typed as `250`, `1.15`, `1,000`, `10.555`, `-5`, letters | Valid amounts are read correctly to the paisa. Invalid ones are refused clearly. No amount is ever rounded silently. |
