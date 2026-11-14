# What is tested where

For the manager and the tech lead. Use it to answer "is this covered?" and to find the steps to re-run after a fix.

Step prefixes: **O** owner · **C** cashier at the till · **W** waiter · **K** kitchen · **G** customer · **M** manager · **D** full day · and the tech checklists **PR** printer · **TL OF AL TM CL** till and offline · **SY** sync · **MT** money · **KD** kitchen display · **GS** guest security · **PM** payments and messages · **RS** roles · **EC** edge cases · **DB** devices · **PC** platform console.

## By part of the product

| Part of the product | Non-tech scripts | Tech checklists |
|---|---|---|
| Signing in: dashboard, till PIN, waiter app, guest code | O-01, C-01 to C-06, W-01 to W-07, G-12 | RS-32 to RS-41, TL-05 to TL-07, PM-15 to PM-19 |
| Business details, outlet, hours, bank | O-06 to O-10 | RS-35, EC-21, PC-04 to PC-09 |
| Menu: dishes, sizes, add-ons, photos, prices, sold out | O-11 to O-23, W-19, W-20, G-02 to G-06, D-24 to D-27 | SY-11, SY-14, OF-13, OF-14, PM-24 to PM-26, EC-10, EC-20 |
| Rooftop and Main Hall prices | O-22, C-54, W-18, D-21 to D-23 | MT-45, MT-46, MT-47 |
| Tables, sections, QR stickers, assignments | O-24 to O-28, C-24, W-08, W-09 | GS-08, SY-10, SY-15 |
| Taking a table order | C-25 to C-30, W-10 to W-17, D-09 to D-12 | EC-07, EC-08, OF-01 |
| Takeaway (pay first, name, token) | C-10 to C-23, W-50 to W-52, D-05 to D-08 | MT-13, PR-04, SY-08 |
| Kitchen tickets, stations, timers, ready, served | K-01 to K-26, W-32, W-36, D-08, D-12 | KD-01 to KD-20, PR-05 to PR-08 |
| Cancelling a dish or an order after the kitchen has it | C-29, W-33, W-34, M-05 to M-07, D-11 | RS-03, KD-10, PR-08 |
| The bill: GST, service charge, packaging, round off | C-10, C-14, C-16, C-31, C-44, C-47, C-54, W-41, W-43, D-13, D-20, D-23 | MT-01 to MT-13, PR-01 to PR-04 |
| Discounts and removing the service charge | C-35 to C-42, M-01 to M-04, D-28 | MT-08, MT-10, MT-14 to MT-19 |
| Paying: cash and change, card, UPI, in parts, split | C-12, C-15, C-17, C-32, C-43 to C-49, W-42 to W-46, D-14 | MT-20 to MT-26, PM-01 to PM-09, EC-06 |
| Moving and joining tables, moving dishes, separate bills | C-51 to C-56, W-37 to W-39, D-09, D-22 | MT-21, MT-46, EC-11 |
| Guests ordering from their phones | G-01 to G-32, W-21 to W-31, C-57 to C-61, M-17, M-18, D-15 to D-20 | GS-01 to GS-26, EC-12 |
| Guest requests (water, bill, ready to order) | G-09, G-19, W-29, W-30, D-19 | EC-27 |
| Takeaway by QR, guests paying from their phones | G-33 to G-35, G-20 | GS-27 to GS-37 |
| Correcting bills: void, walk-out, credit note, refund | C-65, C-67, M-09 to M-16, D-29, D-30 | MT-27 to MT-33, PM-10 to PM-14, PR-14 |
| Bill numbers | C-66, O-66, O-67 | MT-34 to MT-38, SY-02, OF-16 |
| Cash drawer: float, pay in and out, close, difference | C-07 to C-09, C-68 to C-77, M-08, D-02, D-47, D-48 | MT-39, MT-40, PR-16, SY-06 |
| Closing the day: X and Z reports, carrying a table forward | M-29 to M-34, D-45 to D-54 | MT-41 to MT-43, TM-01 to TM-04, PR-15, OF-15 |
| Manager approvals with a PIN | M-01 to M-08, C-42, C-76, W-33 | RS-03, RS-07, RS-13, MT-15, MT-40 |
| The dashboard's POS page in a browser | M-24 to M-28 | RS-38, SY-22 |
| Internet down, and coming back | D-31 to D-41, K-25, W-54 to W-56 | OF-01 to OF-16, SY-18 to SY-21 |
| The till and the dashboard holding the same records | O-49 to O-52, M-35 to M-39, D-40, D-51 | SY-01 to SY-25 |
| Bills, payments and shifts in the dashboard | O-49 to O-53, M-35 to M-39 | SY-01 to SY-09 |
| Customers | O-54, C-50 | RS-29, RS-45, RS-46, EC-24 |
| Bookings and the waitlist | O-55 to O-57, G-36 to G-40, M-23, D-42 to D-44 | EC-17, PM-20 |
| Stock: purchase, receive, recipe, sale, wastage, count | O-38 to O-48 | SY-12, EC-24 |
| Staff: invite, roles, till PINs, removal | O-29 to O-35, M-20, M-21 | RS-01 to RS-24, RS-41, OF-11, OF-12, PM-18 |
| Roster, attendance, leave, payroll | O-36, O-37, W-06, W-59 to W-63, M-22 | OF-07, SY-13 |
| Reports and exports | O-58 to O-63, M-33 | MT-44, SY-23 to SY-25, EC-25, EC-26 |
| Settings, order reasons | O-64 to O-67 | SY-15, SY-16, KD-04 |
| The till as a device, printers, alerts | O-68, C-79 | TL-01 to TL-11, AL-01 to AL-05, PR-25 to PR-36 |
| Printing | — (the tech team's) | PR-01 to PR-36, KD-13, KD-14 |
| Who can do what | C-04, C-65, C-67, C-81, W-07, M-04, M-16 | RS-01 to RS-31 |
| History of changes | O-70 to O-72, M-40, D-52 | RS-42, RS-43 |
| Messages: SMS, WhatsApp, notifications | W-01, O-05, O-29, G-37 | PM-15 to PM-23, EC-27, EC-28 |
| Two people doing the same thing at once | C-23, C-78, W-16, W-46, G-15, G-30, G-39 | EC-01 to EC-12, KD-07 |
| Phones, screen sizes, browsers | O-73, W-57, K-26 | DB-01 to DB-25 |
| Platform console | — | PC-01 to PC-21 |
| Importing menus, customers and stock | — | EC-23, EC-24 |

## The 12 November go-live build

Each item added in that build, and where it is tested.

| Item | Steps |
|---|---|
| Bill numbers: outlet code, 16 characters, never refuse to bill offline | C-66, O-66, O-67, MT-34 to MT-38, OF-16, PC-08 |
| Drawer difference above ₹500 needs a manager's PIN | C-76, M-08, MT-40 |
| Payment methods when the internet is down | D-33, OF-02 |
| Takeaway needs the customer's name; phone optional | C-11, C-12, C-14, W-50 to W-52, SY-08 |
| Carry a table forward to the next day | M-29, M-30, M-34, D-45, D-46, D-53, D-54, TM-04 |
| Card slip number and approval code | C-17, M-36, SY-09 |
| Favourite dishes on a customer's profile | O-54 |
| Replacing a till is refused while the old one runs | TL-03, TL-04 |
| Refund back to UPI from a credit note | M-15, MT-33, PM-10 to PM-13 |
| A bill paid twice: "Refund extra" | M-39, PM-05, GS-31 |
| Bill search across dates | O-50, M-35 |
| Shift history | O-52, M-38, SY-06 |
| Closing a purchase order | O-47 |
| Tenant search in the console | PC-10 |
| Removing a staff member while offline | M-20, OF-11, OF-12 |
| Till alerts as banners | PR-27, PR-36, AL-01 to AL-05 |
| "Order waiting" flag on the floor | C-61, W-28, M-18, D-17 |
| Seating a reserved or cleaning table with a reason | W-11, M-19, D-43 (reserved: see OQ-2) |
| Kitchen display shows what changed | K-11 to K-13, D-11, KD-10, KD-11 |
| Kitchen display paper fallback | KD-13, KD-14 |
| "Ready to order" from the guest's phone | G-09, G-19, W-30 |
| Short codes and the Recent strip on the till | O-18, C-20, C-21 |
| OTP by WhatsApp when SMS fails | PM-17 |
| Photos and files in cloud storage | O-17, PM-24 to PM-26 |
| Refusing payment methods the outlet doesn't take | W-45, D-33 |
| Deactivating an outlet is blocked by open tables and unpaid bills | EC-21 |
| Importing a sheet with names that already exist | EC-23 |

## Not covered by this kit

These need their own proof, outside manual testing. They are listed so nobody assumes otherwise.

- Load: many outlets and many orders at once.
- Backups, restoring from a backup, and disaster recovery.
- The till's installer signing, automatic updates and rollback.
- A security review by a specialist (this kit checks behaviour, not code).
- Features in `KNOWN-LIMITS.md` under "Not in this release".
