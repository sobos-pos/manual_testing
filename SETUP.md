# Setup (tech lead)

The scripts only work on the standard test restaurant in `TEST-RESTAURANT.md`: its totals are written into every money step. This page is how you make the environment match it, and what to check before each round.

Never put a link, login, PIN, key or token in this repo. Send them to each tester privately.

## 1. Round record

Fill this in at the start of every round and commit it. It holds no secrets.

| | Round 1 | Round 2 | Round 3 |
|---|---|---|---|
| Round name (e.g. `R1 2026-11-17`) | | | |
| Backend version (commit) | | | |
| Dashboard and guest app version | | | |
| Till app version | | | |
| Waiter app version | | | |
| Internet at the test site (provider, speed) | | | |
| Till PC, printer models, connection type | | | |
| Phones used for the waiter app | | | |
| Answer check passed (section 6) | | | |

## 2. Build the test restaurant

Use a dedicated test organisation, never a live one.

The demo seed builds exactly the restaurant in `TEST-RESTAURANT.md`: 33 dishes, three kitchen stations, Main Hall and Rooftop (with the Rooftop price list), the Front Counter and six staff. From `backend_api/backend`:

```bash
python manage.py seed_demo
```

It prints demo logins and till PINs. Keep that output private.

If you build it by hand instead, match every name and price on that page. One wrong price makes every tester report a wrong total.

For the owner's pages to have history (bills, reports, stock, bookings, rosters), also run:

```bash
python manage.py seed_dashboard --days 14 --bills-per-day 18
```

```bash
python manage.py seed_dashboard_extras
```

## 3. Settings the scripts rely on

Set these in Dashboard → Settings (search for the name). Everything not listed stays at its default.

| Setting, as the dashboard names it | Set to | Default | Why |
|---|---|---|---|
| Service charge | 10 | 0 | Table bills carry a service charge; the waiver is tested |
| Service charge applies to | Dine-in | Dine-in | Takeaway bills must have none |
| Charge GST on the service charge | On | Off | The charge and its GST must leave together when waived |
| Packaging charge | ₹10 | 0 | Takeaway bills carry a charge |
| Menu prices include GST | Off | Off | Prices are before GST |
| Round off the bill total | On, nearest rupee | On | A visible round-off line |
| Payment buttons on the till | Cash, Card, UPI | Cash, Card, UPI | |
| How guests prove they are seated | QR code or table PIN | Waiter shows a QR code | Both ways are tested |
| Waiter reviews guest orders | On | On | A guest order waits for the waiter |
| Time to accept a guest order | 90 | 90 | "Order waiting" flag |
| Guests pay from their phones | Off | Off | See the note below |
| Lock the till after | 300 | 300 | |
| Discounts above this amount need a manager | ₹500 | ₹500 | |
| Voids above this amount need a manager | ₹500 | ₹500 | |
| Cancelling after the kitchen ticket needs a manager | On | On | |
| Time to void a paid bill | 0 | 0 | A paid bill is corrected by credit note only |
| Drawer difference that needs a manager | ₹500 | ₹500 | |
| Open a drawer before billing | On | On | |
| This till has a cash drawer | On if one is attached | Off | |
| Take reservations | On | Off | Booking steps |
| Online booking page | On | Off | Booking steps |
| Keep a waitlist | On | Off | Waitlist steps |
| Use up stock when an order is confirmed | On | On | Stock falls after a sale |
| Print a payment QR on the bill | Off | Off | `tech/printer.md` turns it on for its own checks |
| Offers, Loyalty points | Off | Off | Not in this release (`KNOWN-LIMITS.md`) |

**If the pilot outlets will let guests pay from their phones,** run `tech/guest-ordering-security.md` GS-27 to GS-33 with that setting on, in a session of its own, then turn it off again.

**If the pilot outlets charge no service charge,** keep these settings anyway. The takeaway orders prove the no-charge arithmetic, and the table orders prove the charge is right when an outlet turns it on.

## 4. People and logins

- **One login per tester.** Two people on one login hide the bugs that only show with two people.
- Give every tester who uses the till their own **till PIN** (Dashboard → Staff & Access → the person → till PIN). The lock screen has no username: the PIN is the person.
- Roles needed: Owner, Manager, Cashier, Waiter (two), Kitchen. Add `TEST` to the name of any extra staff you create.
- For `tech/roles-and-security.md` you also need: a second outlet in the same organisation, a second organisation, and a platform admin login with MFA.
- Note that the seeded **Manager** has the same access as the Owner. `tech/roles-and-security.md` RS-20 creates a narrower outlet-only role to test the difference.

## 5. Equipment

| Station | What it needs |
|---|---|
| Till | A PC with the till app installed and paired to Main Outlet as the Front Counter. Receipt printer, kitchen printer and cash drawer are yours to connect and test (`tech/printer.md`). Non-tech testers use the till's screens; they do not test the printer. |
| Kitchen | The till's kitchen display, on a second screen if you have one. |
| Waiters | Two Android phones with the waiter app, on the same Wi-Fi as the till. |
| Owner and manager | A laptop each, with the dashboard link. |
| Customers | Their own phones, on mobile data. Printed QR stickers for tables 3, 4, 7 and R2. |
| Internet drill | A way to cut the internet without cutting the local network, e.g. unplug the router's internet cable. |

Links to send each tester privately: dashboard, platform console (tech only), the public booking page, and the takeaway QR link if the outlet takes guest takeaway orders.

## 6. Before every round

1. Deploy the builds and fill in the round record.
2. **Start clean:** yesterday's drawer is closed, no table is open, no guest order is waiting, no bill is unpaid.
3. The till shows "Online · all sales sent to Cloud" on its lock screen. Both waiter phones show Connected.
4. Printers print a test slip. The kitchen display opens.
5. **Answer check.** On the till, ring up **Order A** on table 4 and make the bill: it must say **₹785**. Ring up takeaway **T1**: it must say **₹483**. If either differs, fix the setup before anyone starts. Void the table bill and cancel the takeaway.
6. Tell testers the round name. They tell their AI, so every result is recorded against it.

## 7. After every round

1. All tables closed, drawers closed, Z report printed for the day.
2. Run "update triage" (`HOW-IT-WORKS.md`).
3. Before the next round, mark fixed bugs **Fixed** so testers know what to re-check.
