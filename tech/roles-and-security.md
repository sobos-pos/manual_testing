# Roles and security checklist

Use separate browser profiles (not just tabs) for each login, so sessions don't mix.

| ID | Check | Pass when |
|---|---|---|
| RS-01 | Sign in as each role: owner, manager, cashier, waiter | Each only sees the pages and buttons its role allows. |
| RS-02 | As a cashier, paste the address of an owner-only page (settings, staff, analytics) | Blocked with a clear message. No data flashes on screen first. |
| RS-03 | Change a role's permissions while that person is signed in | The change applies at their next action or sign-in, as designed. |
| RS-04 | Remove a staff member while they are signed in | Their next action is refused. They cannot keep working. |
| RS-05 | Two outlets: a staff member of outlet A tries outlet B's pages by address | No access to outlet B's data. |
| RS-06 | A customer changes the table in the QR link or the address | They don't see another table's order or bill. |
| RS-07 | A customer opens an old QR link after their table is closed | They don't see the previous diners' order. |
| RS-08 | Wrong OTP or password many times | The account or phone is limited after several attempts. The message doesn't reveal whether the account exists. |
| RS-09 | OTP reuse, and OTP after it expires | Both refused. |
| RS-10 | Sign out, then Back and refresh | No data is shown. Old links need sign-in. |
| RS-11 | Sensitive actions (void a paid bill, refund, change prices, close the day) | They need the right role, and a PIN or reason where designed. They're recorded in Audit with who and when. |
| RS-12 | Invite links: use twice, use after revoking, use after expiry | Refused cleanly. A new invite works. |
| RS-13 | Personal data in addresses | No phone numbers, emails or tokens appear in page addresses. |
| RS-14 | Error messages | No technical stack traces or internal details shown to users. |
| RS-15 | Platform console without MFA | Requires MFA as designed. |
