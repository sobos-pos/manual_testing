# The test restaurant and the answer sheet

Every script uses the same restaurant, the same menu and the same prices. That is what lets you check money to the rupee: the right total for each standard order is written below. If the app shows a different figure, that is a bug.

The tech lead builds this restaurant before testing starts (`SETUP.md`). **Never rename, reprice or delete anything on this page.** When a script asks you to create something, start its name with `TEST`.

## The place

| | |
|---|---|
| Outlet | Main Outlet |
| Counter (the till) | Front Counter |
| Main Hall | Tables 1, 2, 3, 4 (4 seats) · 5, 6 (2 seats) · 7, 8 (6 seats) |
| Rooftop | Tables R1 (2 seats) · R2, R3 (4 seats) · R4 (6 seats). Every dish costs more here. |
| Kitchen stations | Main Kitchen · Tandoor · Beverage Bar |

## The people

Each tester has their own login. These are the roles you play.

| Person | Role | Works on |
|---|---|---|
| Rohan Mehta | Owner | Dashboard on a laptop |
| Meera Iyer | Manager | Till (PIN), dashboard, approvals |
| Priya Nair | Cashier | Till |
| Wasim Khan, Arjun Reddy | Waiters | Waiter app on a phone |
| Farhan Ali | Kitchen | Kitchen display |
| You or a teammate | Customer | Your own phone |

## Price list

Prices are before GST. Every dish carries GST 5% (CGST 2.5% + SGST 2.5%).

| Dish | Main Hall and takeaway | Rooftop | Goes to |
|---|---|---|---|
| **Starters** | | | |
| Paneer Tikka | ₹280 | ₹310 | Tandoor |
| Hara Bhara Kebab | ₹240 | ₹265 | Main Kitchen |
| Chilli Paneer | ₹260 | ₹290 | Main Kitchen |
| Chicken 65 | ₹290 | ₹320 | Main Kitchen |
| Tandoori Chicken, Half | ₹320 | ₹355 | Tandoor |
| Tandoori Chicken, Full | ₹580 | ₹640 | Tandoor |
| Chicken Tikka | ₹320 | ₹355 | Tandoor |
| **Main Course** | | | |
| Paneer Butter Masala | ₹310 | ₹345 | Main Kitchen |
| Dal Makhani | ₹260 | ₹290 | Main Kitchen |
| Kadai Paneer | ₹300 | ₹330 | Main Kitchen |
| Palak Paneer | ₹290 | ₹320 | Main Kitchen |
| Chana Masala | ₹220 | ₹245 | Main Kitchen |
| Butter Chicken | ₹360 | ₹400 | Main Kitchen |
| Mutton Rogan Josh | ₹420 | ₹465 | Main Kitchen |
| **Breads** | | | |
| Tandoori Roti | ₹40 | ₹45 | Tandoor |
| Butter Naan | ₹70 | ₹80 | Tandoor |
| Garlic Naan | ₹85 | ₹95 | Tandoor |
| Lachha Paratha | ₹75 | ₹85 | Tandoor |
| **Rice & Biryani** | | | |
| Jeera Rice | ₹180 | ₹200 | Main Kitchen |
| Veg Biryani | ₹280 | ₹310 | Main Kitchen |
| Chicken Biryani | ₹340 | ₹375 | Main Kitchen |
| Mutton Biryani | ₹420 | ₹465 | Main Kitchen |
| **South Indian** | | | |
| Masala Dosa | ₹150 | ₹165 | Main Kitchen |
| Idli Sambar | ₹110 | ₹125 | Main Kitchen |
| Medu Vada | ₹120 | ₹135 | Main Kitchen |
| Onion Uttapam | ₹150 | ₹165 | Main Kitchen |
| **Desserts** | | | |
| Gulab Jamun | ₹120 | ₹135 | Main Kitchen |
| Rasmalai | ₹150 | ₹165 | Main Kitchen |
| Gajar ka Halwa | ₹140 | ₹155 | Main Kitchen |
| **Beverages** | | | |
| Masala Chai | ₹60 | ₹70 | Beverage Bar |
| Filter Coffee | ₹70 | ₹80 | Beverage Bar |
| Sweet Lassi | ₹110 | ₹125 | Beverage Bar |
| Mango Lassi | ₹130 | ₹145 | Beverage Bar |
| Fresh Lime Soda | ₹90 | ₹100 | Beverage Bar |

### Extras (all optional)

| Extra | On these dishes | Choices |
|---|---|---|
| Spice level | Curries and biryanis | Mild, Medium, Hot (free) |
| Extras | Paneer Butter Masala, Dal Makhani, Kadai Paneer, Palak Paneer, Butter Chicken | Extra butter ₹30, Extra cream ₹30 |
| Sides | Biryanis | Raita ₹50, Mirchi ka salan ₹40 |
| Add-ons | Masala Dosa, Onion Uttapam | Cheese ₹40, Ghee roast ₹30 |
| Sugar | Masala Chai, Filter Coffee | Regular, Less sugar, No sugar (free) |
| Style | Fresh Lime Soda | Sweet, Salted, Mixed (free) |

## How a bill adds up

1. **Subtotal:** the dishes and their extras.
2. **Discount,** if any, comes off before anything else is worked out.
3. **Service charge: 10%, on table bills only.** Takeaway has none. The guest may refuse it, and the cashier can remove it without a manager.
4. **Packaging: ₹10 on every takeaway bill.**
5. **GST 5%** on the dishes, on the service charge and on the packaging. It shows as CGST and SGST, half each.
6. **Round off** to the nearest rupee, shown as its own line.
7. **To pay.**

On a table, the service charge appears when the bill is made, not while the table is still ordering.

## The answer sheet

Enter each dish once and set its quantity. If the same dish is added in two separate rounds, GST may differ by a paisa or two; **To pay must still match.**

### Table orders (Main Hall unless it says Rooftop)

| Order | Dishes | Subtotal | Service charge | GST | Round off | **To pay** |
|---|---|---|---|---|---|---|
| **A** Lunch for two | 1 Butter Chicken, 2 Butter Naan, 1 Jeera Rice | ₹680.00 | ₹68.00 | ₹37.40 | −₹0.40 | **₹785** |
| **A, service charge removed** | same | ₹680.00 | none | ₹34.00 | none | **₹714** |
| **B** Tea-time | 3 Garlic Naan, 2 Masala Chai | ₹375.00 | ₹37.50 | ₹20.64 | −₹0.14 | **₹433** |
| **C** With an extra | 1 Paneer Butter Masala with Extra butter, 1 Dal Makhani, 4 Tandoori Roti, 2 Fresh Lime Soda | ₹940.00 | ₹94.00 | ₹51.70 | +₹0.30 | **₹1,086** |
| **D** Family dinner | 1 Paneer Tikka, 1 Chicken 65, 2 Butter Chicken, 1 Dal Makhani, 6 Butter Naan, 2 Jeera Rice, 3 Gulab Jamun | ₹2,690.00 | ₹269.00 | ₹147.96 | +₹0.04 | **₹3,107** |
| **E** Before the discount | 2 Mutton Biryani, 1 Chicken Tikka, 2 Mango Lassi | ₹1,420.00 | ₹142.00 | ₹78.10 | −₹0.10 | **₹1,640** |
| **E, with 10% off** | same, discount ₹142.00 | ₹1,420.00 | ₹127.80 | ₹70.30 | −₹0.10 | **₹1,476** |
| **F** Rooftop | 1 Butter Chicken, 2 Garlic Naan, 2 Mango Lassi at Rooftop prices | ₹880.00 | ₹88.00 | ₹48.40 | −₹0.40 | **₹1,016** |
| **G** Guest phone order | Round 1: 2 Masala Dosa, 2 Filter Coffee. Round 2: 1 Rasmalai | ₹590.00 | ₹59.00 | ₹32.46 | −₹0.46 | **₹681** |
| **H** Party moves upstairs | In Main Hall: 1 Butter Chicken, 2 Butter Naan. After moving to the Rooftop: 2 Mango Lassi | ₹790.00 | ₹79.00 | ₹43.46 | −₹0.46 | **₹912** |

- **Order D split three ways:** ₹1,035.67 + ₹1,035.67 + ₹1,035.66. The three parts must add up to exactly ₹3,107.
- **Order F** in the Main Hall would be ₹912. If the Rooftop bill shows ₹912, the Rooftop prices are not being used.
- **Order H:** the first round keeps Main Hall prices (₹360, ₹70). Only the lassis ordered after the move cost the Rooftop price (₹145 each).

### Takeaway orders

| Order | Dishes | Subtotal | Packaging | GST | Round off | **To pay** |
|---|---|---|---|---|---|---|
| **T1** | 1 Chicken Biryani, 1 Sweet Lassi | ₹450.00 | ₹10.00 | ₹23.00 | none | **₹483** |
| **T2** | 1 Masala Dosa with Cheese, 1 Filter Coffee | ₹260.00 | ₹10.00 | ₹13.50 | +₹0.50 | **₹284** |
| **T3** Office order | 4 Chicken Biryani, 2 Veg Biryani, 6 Gulab Jamun | ₹2,640.00 | ₹10.00 | ₹132.50 | +₹0.50 | **₹2,783** |

- **T1 paid with ₹500 cash:** change ₹17.
- **Credit note for the Sweet Lassi on T1:** ₹115.50 (₹110 plus ₹5.50 GST).

## Limits you will meet

| Rule | Value |
|---|---|
| The till locks itself after | 5 minutes without a tap |
| Wrong PINs before a person is locked out | 5 |
| A discount, or a void, above this needs a manager's PIN | ₹500 |
| A cash drawer short or over by more than this needs a manager's PIN | ₹500 |
| A guest's phone order must be accepted within | 90 seconds, then it shows "Order waiting" |
| The waiter's pairing code lasts about | 2 minutes |
| A UPI QR on the till lasts | 5 minutes |
| A kitchen ticket turns "Aging" at, and "Late" at | 15 minutes, 20 minutes |
| A table shows "Cleaning" for | 5 minutes after the guests leave |
| Largest party for a booking | 12 |
| The business day changes at | 5 am |

## Payment methods

The till takes **Cash**, **Card** and **UPI**. Pay only the way the tech lead tells you:

- **Cash:** play money. Count it properly, because the drawer must balance.
- **Card:** the bank's card machine is separate. On the till you only confirm that the card was approved.
- **UPI:** either the test QR the till shows, or "Guest paid by UPI · mark paid".

Never pay real money unless the tech lead tells you to.
