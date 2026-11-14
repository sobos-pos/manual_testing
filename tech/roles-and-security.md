# Roles and security checklist

**Setup:** one login for each role (Owner, Manager, Cashier, Waiter, Kitchen), a second outlet in the same organisation, a second organisation with its own data, and a platform admin login. Use a separate browser profile (not just a tab) for each login, so sessions don't mix.

## What each role can do

Sign in as each role and try each action, on the till, in the waiter app and in the dashboard. A refused action must show a clear message and change nothing.

| ID | Action | Owner, Manager | Cashier | Waiter | Kitchen |
|---|---|---|---|---|---|
| RS-01 | Take an order, send it to the kitchen | Yes | Yes | Yes | No |
| RS-02 | Accept or decline a guest's phone order | Yes, any table | Yes | Own tables only | No |
| RS-03 | Cancel a dish after it went to the kitchen | Yes | Yes, with a manager's PIN at ₹500 or more | Only with a manager's PIN | No |
| RS-04 | Mark a dish sold out | Yes | Yes | Yes | Yes |
| RS-05 | Mark a kitchen ticket ready | Yes | No | No | Yes |
| RS-06 | Take payment and settle a bill | Yes | Yes | Yes | No |
| RS-07 | Give a discount | Yes | Yes, up to ₹500 | No | No |
| RS-08 | Remove the service charge | Yes | Yes | No | No |
| RS-09 | Split a bill into separate bills | Yes | Yes | No | No |
| RS-10 | Void an unpaid bill, record a walk-out | Yes | No | No | No |
| RS-11 | Issue a credit note, refund a payment | Yes | No | No | No |
| RS-12 | Open and close the cash drawer, pay in and out | Yes | Yes | No | No |
| RS-13 | Approve a drawer difference above ₹500 | Yes | No | No | No |
| RS-14 | Run the Z report, carry a table forward | Yes | No | No | No |
| RS-15 | Move or join tables, close an empty table | Yes | Yes | Yes | No |
| RS-16 | Change the menu or a price | Yes | No | No | No |
| RS-17 | See reports, the audit trail, staff and payroll | Yes | No | No | No |
| RS-18 | Invite staff, edit roles, set till PINs | Yes | No | No | No |
| RS-19 | Change settings, printers, the floor plan | Yes | No | No | No |

## Narrower roles and limits

| ID | Check | Pass when |
|---|---|---|
| RS-20 | Create a role "TEST Outlet Manager" that manages one outlet but cannot edit bank details, plan, integrations or payroll. Sign in as it | Those pages are absent or refused. Everything else a manager needs works. |
| RS-21 | As that outlet manager, create a role and try to give it a permission you do not hold | Refused. A person can never hand out more than they have. |
| RS-22 | As that outlet manager, invite someone as Owner, or to the other outlet | Refused. |
| RS-23 | As that outlet manager, edit the built-in Owner or Manager roles, or a role used at the other outlet | Refused. |
| RS-24 | Change a role's permissions while a person with it is signed in | Dashboard: applies at their next action. Till and waiter app: applies within a few minutes, without signing in again. |

## Getting in where you shouldn't

| ID | Check | Pass when |
|---|---|---|
| RS-25 | As a cashier, paste the address of an owner-only dashboard page (settings, staff, reports, audit) | Blocked with a clear message. No data flashes on screen first. The data is not in the network responses either. |
| RS-26 | As staff of Main Outlet only, open the second outlet's pages and records by address, and by changing an ID in the address | No access to the second outlet's orders, bills, staff, stock or customers. |
| RS-27 | As the owner of organisation A, open a record from organisation B by its ID | Not found. Nothing from B is shown, counted or hinted at, in any list, search, report or export. |
| RS-28 | Search customers, bills and staff for a name that exists only in organisation B | No results. |
| RS-29 | Customers across outlets of one organisation | One shared customer list, by design. A guest of outlet 1 is found at outlet 2. |
| RS-30 | As a restaurant owner, open the platform console | Refused. |
| RS-31 | Every record ID seen in page addresses and network responses | Random-looking with a prefix. Never 1, 2, 3. |

## Signing in

| ID | Check | Pass when |
|---|---|---|
| RS-32 | Wrong password or code many times | Limited after about 5 tries, with a wait that grows. The message never reveals whether the account exists. |
| RS-33 | A one-time code used twice, and after it expires | Both refused. |
| RS-34 | Owner sign-in | A code from an authenticator app is required. It cannot be skipped. Recovery codes work once each. |
| RS-35 | As the owner, long after signing in: change bank details, export customers, erase a customer, edit a role, change Razorpay keys | Each asks you to confirm it's you again first. |
| RS-36 | Account → Devices | Every signed-in device is listed. Signing one out ends it at once. "Sign out everywhere" works. |
| RS-37 | Sign out, then Back and refresh; open a saved link | No data is shown. Old links need sign-in. |
| RS-38 | Leave the dashboard's POS page idle for 6 minutes | It signs out, like the till locking. |
| RS-39 | A till PIN typed into the dashboard's sign-in | It does not work. A PIN only ever unlocks a till. |
| RS-40 | Two staff with the same till PIN | The second is refused when it is set. |
| RS-41 | Remove a staff member while they are signed in to the dashboard, the waiter app and the till | Dashboard: refused at the next action. Waiter app and till: refused within a few minutes, and at once when a manager revokes them on the till itself. |

## Traces

| ID | Check | Pass when |
|---|---|---|
| RS-42 | Sensitive actions: discount, void, walk-out, credit note, refund, waiver, price change, role change, staff removal, drawer difference approval, table carried forward | Each is in the audit trail with what, when, who did it and who approved it. |
| RS-43 | The audit trail itself | No entry can be edited or deleted by anyone, including the owner. |
| RS-44 | Page addresses, error messages and exported files | No phone number, email or token in an address. No technical stack trace or internal name in a message shown to a user. Every error shows a short reference code. |
| RS-45 | Customer data: export all customers, and erase one customer | Owner only. Erasing removes the person's name and phone everywhere but leaves their bills intact and unnamed. |
| RS-46 | A staff member with no customer access (a waiter) | Never sees a guest's full phone number. |
