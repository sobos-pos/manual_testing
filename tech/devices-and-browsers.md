# Devices and browsers checklist

Run the main flows (sign in, menu, order, bill, pay) on each combination. Record the device model and browser version in each bug.

| ID | App | Where | Pass when |
|---|---|---|---|
| DB-01 | Owner dashboard | Chrome, Edge and Firefox on Windows. Safari on Mac if available. | Everything works and looks the same. |
| DB-02 | Owner dashboard | Laptop 1366×768, desktop 1920×1080, tablet in both orientations | No cut-off content. No sideways scrolling. Tables are readable. |
| DB-03 | Owner dashboard | Browser zoom at 125% and 150% | Still usable. |
| DB-04 | Cashier POS (web) | Touch tablet | Buttons are big enough to tap. No hover-only actions. |
| DB-05 | Customer QR ordering | Android Chrome (cheap and new phones), iPhone Safari | Menu, cart, OTP and payment all work. The keyboard doesn't hide the buttons. |
| DB-06 | Customer QR ordering | Small screen (360 px wide) and large phone | Readable. No overlapping parts. |
| DB-07 | Customer QR ordering | Scanning with the phone camera, Google Lens and a UPI app's scanner | The menu opens each time. |
| DB-08 | Waiter app | Android 10 to the latest. Low-memory phone. | Installs, signs in, and stays responsive through a full service. |
| DB-09 | Waiter app | Phone battery saver on, app in the background for 10 minutes | Notifications still arrive. The app resumes correctly. |
| DB-10 | All | Dark mode on the device | Text is readable, or the app stays in light mode cleanly. |
| DB-11 | All | Indian network speeds: 4G, weak 4G, public Wi-Fi | Usable. Clear messages when slow. |
