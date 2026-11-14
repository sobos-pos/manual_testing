# Go-live sign-off

SoBoss goes to a real restaurant only when every condition on this page is met on the **release build**: the exact versions written in the final round's record in `SETUP.md`. A fix after that means a new build, a new round, and this page again.

Ask an AI "go-live check" (see `AGENTS.md`) for a report of what stands in the way. People tick the boxes; the AI does not.

## 1. Everything was tested

- [ ] Every step of scripts 1 to 6 has a result from at least one tester in round R1 or later. No step is "not run".
- [ ] Every item of every `tech/` checklist has a result. The "Two tills" items and the guest-payment items may be Skipped if the pilot does not use them.
- [ ] Every **Blocked** step was unblocked and run, or the owner accepts in writing below why it was not.
- [ ] Every **Not there** step is explained by `KNOWN-LIMITS.md`, or has a bug.

## 2. No serious bug is open

- [ ] No open P0.
- [ ] No open P1.
- [ ] Every P0 ever raised has **Retest passed**, by the tester who found it.
- [ ] The owner has read the list of open P2 bugs and accepts going live with them.
- [ ] No bug is waiting as "Needs owner decision".

## 3. The money is right

On the release build:

- [ ] The answer check passes: order A is ₹785 and T1 is ₹483, on the till and in the waiter app.
- [ ] Every standard order on the answer sheet was rung up and matched: A to H and T1 to T3.
- [ ] Script 7 (a full day) was run from opening to the next morning, and its final table matched in all three places: the Z report, the dashboard, and the testers' cash sheets. ₹10,483.00 collected, ₹3,514.50 in the drawer.
- [ ] It matched on **two** full days in a row (the second day settles the table carried forward from the first).
- [ ] No bill number was repeated in any round.

## 4. It keeps working when things fail

On the release build:

- [ ] Internet off for 20 minutes during service (script 7, scene 8): the till, the waiter app and the kitchen kept working, and every offline bill reached the dashboard once.
- [ ] Internet off for an hour or more with at least 30 bills (`tech/till-and-offline.md` OF-10): the same.
- [ ] The till was killed and restarted mid-service (TL-09, TL-10): nothing lost, nothing doubled.
- [ ] The printer was switched off and on mid-service (PR-25, PR-26): tickets printed once.

## 5. The real hardware

- [ ] `tech/printer.md` passed on the same printer models, paper width and connection type the pilot outlet uses.
- [ ] The cash drawer opens on cash only.
- [ ] The waiter app passed on the phone models the pilot outlet's waiters use.
- [ ] The till passed on a PC no faster than the pilot outlet's.

## 6. The outside services, live

These cannot be proved on test data. Do each once, for real, before the first guest.

- [ ] Razorpay in **live** mode: one ₹1 UPI payment on the till's QR, confirmed by itself.
- [ ] That ₹1 refunded from a credit note, and the refund arrived.
- [ ] A staff sign-in code arrived by SMS on a real number, from the approved sender.
- [ ] The WhatsApp fallback delivered a code when SMS was switched off (if WhatsApp is set up).
- [ ] A dish photo uploaded in production shows on the guest menu.
- [ ] The production restaurant has no demo staff, demo dishes or test bills, and its first bill number starts where the owner expects.
- [ ] The outlet's legal name, GSTIN, FSSAI number and address print correctly on a bill.

## 7. Open questions are decided

From `KNOWN-LIMITS.md`. Each needs the owner's answer before going live.

| ID | Question | Decision | Decided by, date |
|---|---|---|---|
| OQ-1 | Is the service charge recalculated after a discount? | | |
| OQ-2 | Should a booked table show as Reserved on the till? | | |
| OQ-3 | Is the day closed from the till only? | | |

## 8. The pilot outlet is ready

- [ ] Its menu, prices, taxes, service charge and packaging charge were entered and read back by the owner.
- [ ] Every staff member has their own login and till PIN, and has clocked in once.
- [ ] The cashier and one waiter have each run a practice sale and a practice drawer close.
- [ ] The manager has done one approval, one credit note and one day close.
- [ ] Someone on the tech team is reachable during the first week's opening hours.

## Sign-off

| | Name | Date | Signature or "approved" |
|---|---|---|---|
| Release build (backend, web, till, waiter app) | | | |
| Tech lead: sections 1 to 6 are true | | | |
| Manager: the testers' results are complete | | | |
| Owner: go live | | | |

Accepted exceptions (anything above left unticked, and why):

-
