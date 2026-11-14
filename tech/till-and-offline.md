# Till and offline checklist

**Setup:** the till PC, two waiter phones on the same network, and a way to cut the internet without cutting the local network (e.g. unplug the router's internet cable). For OF-12 and OF-13 you also need to be able to change things in the dashboard from a phone on mobile data while the outlet is offline.

## Installing and signing in

| ID | Check | Pass when |
|---|---|---|
| TL-01 | Install the till app on a fresh PC | It installs and starts. The setup wizard asks a manager to sign in (with their authenticator code where one is set) and to choose the outlet. |
| TL-02 | Finish the wizard: this till takes payments, bills print on the receipt printer | The till is paired to Main Outlet as the Front Counter. It appears in Dashboard → Node & Devices as online within a minute. |
| TL-03 | Run the wizard on a second PC and choose to replace the first till while the first is still running | Refused, with the message that the till is still running: shut it down, wait until it shows offline, then replace it. |
| TL-04 | Shut the first till down, wait until the dashboard shows it offline, then replace it | The new PC takes over the same till. Its name and history stay the same. The old PC can no longer sell. |
| TL-05 | Unlock with a correct PIN, then a wrong PIN five times | The correct PIN opens the till as that person. After five wrong PINs that person is locked out with a countdown. Another person's PIN still works. |
| TL-06 | Leave the till untouched for 5 minutes | It locks. Change "Lock the till after" to 60 seconds in the dashboard: the till follows within a few minutes. Change it back. |
| TL-07 | Unlock as a cashier, then as a manager, and open the back office | Each sees only what their role allows. The back office opens signed in as that person, with Main Outlet only. Locking the till signs the back office out. |
| TL-08 | Open This device as a cashier, then as a manager | The cashier cannot change device settings. A reset or un-pair asks for a manager's PIN and a clear confirmation. |
| TL-09 | Kill the till app during a settle, then start it again | The bill is either fully paid or not paid. Never half: no payment without a bill, no bill number used twice. |
| TL-10 | Restart the PC | The till starts by itself and returns to the lock screen. Open tables, unpaid bills and the open drawer are all still there. |
| TL-11 | Waiter phones find the till | "Find till" finds it within a few seconds with no address typed. After the till's IP address changes, the phones reconnect by themselves or after one tap. |

## Internet down

| ID | Check | Pass when |
|---|---|---|
| OF-01 | Cut the internet. Take table orders from the waiter app and the till | Ordering, kitchen tickets, the kitchen display and billing keep working on the local network, as fast as before. |
| OF-02 | Open the payment screen while offline | Cash, Card and UPI marked by hand are offered. The online UPI QR is greyed out with "Needs internet". Trying an online method by any other route is refused with the same reason. |
| OF-03 | Settle order A in cash and order B by card while offline | Both settle, with bill numbers that continue from the last online bill. |
| OF-04 | Look at the till's lock screen and top bar while offline | It says the till is offline and that sales stay on this till until it reconnects. A back-office page says it needs the internet and that selling still works. |
| OF-05 | A guest tries to order from their phone while the outlet is offline | A clear message within about 5 seconds: ordering is unavailable, the waiter will take the order. No order appears later. |
| OF-06 | A waiter who is already signed in keeps working. A waiter who signs in fresh during the outage | The signed-in waiter works normally. The fresh sign-in is refused with a message that signing in needs the internet. |
| OF-07 | Clock a waiter in and out during the outage | Both punches are taken. After reconnect they are in the dashboard with the right times. |
| OF-08 | Restart the till while offline | It comes back with all open tables, unpaid bills, the drawer and every unsent sale. |
| OF-09 | Bring the internet back | The till says it is online and that all sales are sent, within a few minutes. See `sync-and-reconciliation.md` for the comparison. |
| OF-10 | Stay offline for 1 hour or more, selling at least 30 bills, then reconnect | The full backlog arrives. No bill number repeats. Nothing is missing or doubled. |
| OF-11 | In the till's manager area, revoke a staff member's access while offline | Their PIN is refused at once and their waiter app stops at its next action. After reconnect, the dashboard shows the person removed from the outlet, and the audit trail records who did it and why. |
| OF-12 | Remove a staff member in the dashboard while the outlet is offline, then reconnect | Their PIN and waiter app stop working on the till within a few minutes of reconnecting. |
| OF-13 | Change a `TEST` dish's price in the dashboard while the outlet is offline | The till keeps the old price until it reconnects, then takes the new one. Bills already made keep the price they were made at. |
| OF-14 | Mark a dish sold out on the till while offline | It is sold out on the till and the waiter app at once. After reconnect it is sold out in the dashboard and on the guest menu too. |
| OF-15 | Close the drawer and print the X and Z reports while offline | The drawer closes and the reports print with the right figures. After reconnect, the dashboard's Shifts and Day end show the same. |
| OF-16 | Offline bill numbers when the till has used up its block of numbers (only if you can force it, e.g. by a small block size on a test build) | The till never refuses to bill. It carries on with numbers in the fallback form (outlet code, year, till code, four digits, e.g. `KOR-2627-T1-0001`), 16 characters or fewer, never repeating. |

## Alerts on the till

| ID | Check | Pass when |
|---|---|---|
| AL-01 | Printer off for over a minute | A banner on the till screen names the problem. It clears by itself when fixed. |
| AL-02 | A kitchen ticket waiting more than 2 minutes to be sent | A banner says a kitchen ticket was not sent. |
| AL-03 | Internet off for over 30 seconds | The till shows it is offline. Dashboard → Node & Devices → Alerts shows the till as offline once another device can see it. |
| AL-04 | Each alert while the internet is down | The banners still work. They do not depend on the cloud. |
| AL-05 | The same problem lasting 10 minutes | One banner, not a new one every few seconds. |

## Time and dates

| ID | Check | Pass when |
|---|---|---|
| TM-01 | Sell just before and just after midnight | Both sales belong to the same business day: the day changes at 5 am, not at midnight. |
| TM-02 | Sell just before and just after 5 am (or set "Business day starts at" to the next hour for the test, then set it back) | Each sale lands on the right business day in the X and Z reports and in the dashboard. |
| TM-03 | Set the till PC's clock 10 minutes wrong | Bills still carry a sensible time, or the till warns. Timers on the kitchen display do not go negative. |
| TM-04 | A table still dining when the day is closed | The day cannot close until the table is paid, voided or carried forward with a reason. A carried-forward table's sale counts on the day it is paid. Two Z reports in a row add up with no gap and no double count. |
| TM-05 | Every time shown on the till, waiter app, dashboard and paper | Indian time, in one format. Never UTC. |

## Two tills

**Not part of this release.** Every pilot outlet has one till. Run these only if a second till is installed, and record results as information, not as release blockers.

| ID | Check | Pass when |
|---|---|---|
| CL-01 | Two tills at one outlet | Both see the same tables and orders. Each has its own counter and drawer. |
| CL-02 | Both tills bill different tables at the same time | Bill numbers never clash. |
| CL-03 | The main till is switched off during service | Note what happens. Sales made by a till that takes over while the internet is down is an open decision. |
