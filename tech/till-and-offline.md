# Till and offline checklist

**Setup:** one or two till PCs with the till app, on the same network as the waiter phones, plus a way to cut the internet without cutting the local network (e.g. unplug the router's internet cable).

## Till basics

| ID | Check | Pass when |
|---|---|---|
| TL-01 | Install or update the till app on a fresh PC | It installs and starts. A clear first-time setup links it to the right outlet. |
| TL-02 | Sign in with a staff PIN | A correct PIN works. A wrong PIN is refused. Repeated wrong PINs are handled sensibly. |
| TL-03 | Open the back office from the till | It opens signed in, with the right outlet. |
| TL-04 | Counter sale paid in cash with change | Change is right. The drawer opens. The sale shows in reports. |
| TL-05 | Open a drawer with a counted float | The float is recorded. |
| TL-06 | Cash in and cash out with reasons | They are recorded with reasons. The drawer total changes correctly. |
| TL-07 | Close the drawer: count cash, see over or short | Expected and counted amounts and the difference are right. |
| TL-08 | X report mid-day, Z report at day end | Totals are right. You can't sell into a closed day. The next day starts cleanly. |
| TL-09 | UPI payment at the till (dynamic QR) | The QR shows the right amount. The paid status arrives. Expiry is handled. |
| TL-10 | UPI marked paid by hand | It's recorded as hand-marked, with who did it. |
| TL-11 | Waiter phones connect to the till on the local network | They connect within a few seconds. Orders flow both ways. |

## Internet down

| ID | Check | Pass when |
|---|---|---|
| OF-01 | Cut the internet. Take table orders from the waiter app and the till. | Ordering, KOT printing and billing keep working on the local network. |
| OF-02 | While offline, settle bills in cash and UPI-by-hand | Settled locally. Clearly marked as waiting to sync. |
| OF-03 | Bring the internet back | Everything syncs to the cloud within a few minutes. No duplicates, nothing missing. Compare bill counts and totals on the till and the dashboard. |
| OF-04 | Customer QR ordering while offline | The customer gets a clear message. No ghost orders appear later. |
| OF-05 | Restart the till while offline | It comes back with all open tables and unsynced bills. |
| OF-06 | Internet down for 1 hour or more, then back | The full backlog syncs. Bill numbers stay continuous with no gaps or repeats. |
| OF-07 | Close the day (Z report) while offline | Either it's allowed and syncs later, or it's clearly blocked with a reason. |

## Two tills

| ID | Check | Pass when |
|---|---|---|
| CL-01 | Two tills at one outlet | Both see the same tables and orders. |
| CL-02 | Turn off the main (leader) till during service | The other till takes over within a reasonable time. Waiter phones reconnect. No lost orders. |
| CL-03 | Turn the first till back on | It rejoins without duplicating orders. |
| CL-04 | Both tills bill different tables at the same time | Bill numbers don't clash. |

## Time and dates

| ID | Check | Pass when |
|---|---|---|
| TM-01 | Sell just before and just after midnight IST | Each sale lands on the right business date in reports. |
| TM-02 | Till PC clock set wrong by a few minutes | Bills still use a sensible time, or a warning shows. |
| TM-03 | A table still dining past day-end | It's handled per the rules: carried forward or blocked, with a clear message. |
