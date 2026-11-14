# Kitchen display checklist

The non-tech kitchen script (`../scripts/4-kitchen-screen.md`) covers a cook's normal day. This checklist covers what a cook cannot set up: settings, disconnections, a second screen and the paper fallback.

**Setup:** the till with its kitchen display open, a second screen or PC showing the display if you have one, the kitchen printer, and a helper sending orders from the till.

| ID | Check | Pass when |
|---|---|---|
| KD-01 | Open the display on a paired till, then on a till that is not set up | The paired till shows the board. The other says clearly that there is no kitchen board to show. |
| KD-02 | Open the display with 10 tickets already open | All 10 load at once, with timers showing their real age, not starting from zero. |
| KD-03 | Ticket arrival time | A ticket appears within about half a second of "Send to kitchen" on the till, and within about a second from the waiter app. |
| KD-04 | In the dashboard, change "Warn about a ticket after" to 60 seconds and "Mark a ticket late after" to 120 seconds | Every open display re-colours within a minute or two, without a restart. A ticket turns Aging at 1 minute and Late at 2. **Set both back to 900 and 1200.** |
| KD-05 | The late sound | It plays once when a ticket becomes late, not every second. A display that cannot play sound still shows the ticket as late and counts it. |
| KD-06 | A dish whose category has no station, or a `TEST` dish sent to a `TEST` station with no printer | The ticket still reaches a display or a printer. Nothing is silently dropped. |
| KD-07 | Bump the same ticket from two displays at the same moment | It is bumped once. Both displays agree. |
| KD-08 | Bump a ticket, then undo it within 60 seconds, then try after 60 seconds | Within the window it returns with its timer running. After the window there is no undo, or it is refused clearly. |
| KD-09 | Open the display as a waiter or cashier (no kitchen permission) | "Read only". Tickets cannot be bumped by any route. |
| KD-10 | Quantity reduced from 3 to 2 after sending; a dish added in a later round; a dish cancelled | "3 → 2", NEW, and a struck-through line with a sound. The paper ticket for the same changes is unchanged from today's format. |
| KD-11 | The waiter app's Kitchen tab for the same tickets | It shows the same NEW, "3 → 2" and struck-through lines. It has no bump button. |
| KD-12 | Disconnect the display from the till for 10 seconds (pull its network, or pause the till's server), then reconnect | A "connection lost" banner shows, then clears. The board catches up: no ticket missing, none doubled. Timers kept counting while disconnected. |
| KD-13 | **Paper fallback.** Close every kitchen display for more than 20 seconds, then send two orders | The new tickets print on paper at the station's printer (or the till's own printer where the station has none). |
| KD-14 | Open the display again | Tickets sent while it was closed are on the board. They are **not** printed a second time. New tickets stop printing as fallback. |
| KD-15 | 50 open tickets | The board stays quick to scroll and bump. The station filter still works. |
| KD-16 | Restart the till with tickets open | After the restart every open ticket is back with its real age. Bumped tickets stay bumped. |
| KD-17 | Internet off | Everything above works the same. The display reads the till, not the cloud. |
| KD-18 | A takeaway sold on the till, one sold from the waiter app, and one guest order accepted by a waiter | All three reach the display with the right label: takeaway with name or token, table with its number. |
| KD-19 | A guest order that is waiting for the waiter, or was declined | It never appears on the display. |
| KD-20 | The display left open for a full 3-hour session | No slowdown, no frozen timers, no memory warning. |
