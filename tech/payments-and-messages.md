# Payments and messages checklist

Covers the parts that depend on an outside service: Razorpay for UPI, MSG91 for SMS and WhatsApp, and file storage for photos.

**Setup:** Razorpay bound in Dashboard → Integrations in **test mode**, with a UPI app or the test tool that can pay a test QR. Test phone numbers that really receive SMS. Before the pilot, the owner also runs one ₹1 live payment and one live refund; record that in `../GO-LIVE.md`.

## UPI QR on the till

| ID | Check | Pass when |
|---|---|---|
| PM-01 | Choose UPI on **order A** | A QR appears for exactly ₹785, with a countdown from 5 minutes. |
| PM-02 | Pay it | The till marks the bill paid by UPI by itself within a few seconds. No one has to press "mark paid". The bill has one payment. |
| PM-03 | Let a QR expire without paying | "This QR has expired." The bill is still unpaid. "New QR" gives a fresh one, and the old one can no longer be paid. |
| PM-04 | Pay a QR after it has expired, or pay and then settle the bill another way | The money is not lost: it is listed in Dashboard → Orders & Billing → Day end as UPI money that reached no bill, for a manager to refund. It is never attached to a bill by a guess. |
| PM-05 | Pay the same bill twice (two phones) | The bill stays settled once. The extra payment is listed for a manager, with "Refund extra" for exactly the extra amount. It is never refunded automatically. |
| PM-06 | Split a bill three ways and show a QR for one share | The QR is for that share only (₹362 on order C). |
| PM-07 | "Guest paid by UPI · mark paid" | Settles as UPI with no manager PIN. The bill records who marked it, and can be told apart from a confirmed payment. |
| PM-08 | Internet off, or Razorpay not bound | No QR is offered. Marking UPI by hand still works. The till never fails at the moment of payment. |
| PM-09 | Dashboard → Integrations and Payments & Tenders | Whether Razorpay is connected, and in test or live mode. No key or secret is ever shown, in the page or in its network responses. |

## Refunds

| ID | Check | Pass when |
|---|---|---|
| PM-10 | Credit note on a bill paid by the till's QR, refunded back to UPI | The till says the refund was initiated. In the dashboard the bill shows the refund as initiated, then processed. The test payment is refunded once. |
| PM-11 | Refund from the dashboard: open the bill, Refund on the Razorpay payment, with a reason | Needs the manager or owner. A reason is required. The amount cannot exceed what is left to refund. |
| PM-12 | Two partial refunds that together exceed the payment | The second is refused or capped. |
| PM-13 | Refund while Razorpay cannot be reached | The refund waits and is sent later. It is never shown as processed until Razorpay says so, and never sent twice. |
| PM-14 | Refund a bill paid by card on the bank's machine | No online refund is offered: that money never went through Razorpay. Cash or the bank's own machine is the route. |

## One-time codes and other messages

| ID | Check | Pass when |
|---|---|---|
| PM-15 | Staff sign-in code | Arrives by SMS within a minute. Works once. Expires after about 5 minutes. Five wrong tries cancel it. |
| PM-16 | Ask for codes repeatedly for one number | After a few, further requests are refused for a while with a clear message. |
| PM-17 | SMS fails or is not set up, with WhatsApp set up | The same code arrives on WhatsApp instead. Never two different live codes. |
| PM-18 | Staff invite | The SMS or email arrives with a working link. The link works once and for 7 days. Sending again replaces the old link. |
| PM-19 | Guest sign-in code on the ordering page | Same rules as PM-15. |
| PM-20 | Booking confirmation, and reminders if switched on | Arrive once, with the right restaurant, date, time and party size. |
| PM-21 | Takeaway "ready" message, when the customer gave a phone number | Arrives once, when the kitchen marks the order ready. |
| PM-22 | Every message's wording | Correct spelling, the restaurant's real name, no placeholder text, no internal codes. |
| PM-23 | Logs and the audit trail | Never contain a one-time code, a full phone number or a message body. |

## Photos and files

| ID | Check | Pass when |
|---|---|---|
| PM-24 | Upload a dish photo (JPG and PNG, small and 5 MB) | It saves and shows in the dashboard, on the guest menu and on the till within a minute or two. A file that is too large or not an image is refused clearly. |
| PM-25 | The photo's address, opened in a private window | It loads for the guest menu. A private file (an export, an import sheet) cannot be opened by anyone who is not signed in with the right role. |
| PM-26 | Replace and remove a photo | The old photo is no longer shown anywhere. |
