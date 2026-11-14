# Edge cases checklist

| ID | Check | Pass when |
|---|---|---|
| EC-01 | Double-click every "save", "send", "pay" and "settle" button | Only one action happens. |
| EC-02 | Refresh in the middle of every multi-step flow (order, pay, invite, onboarding) | No duplicates, no half-saved records. The user can continue or restart cleanly. |
| EC-03 | Browser Back after saving or paying | No re-submission. The page shows the current state. |
| EC-04 | The same record open in two tabs: edit in both, save both | The second save is warned, or wins cleanly. No silent data loss. |
| EC-05 | Two users editing the same menu item, table or bill at once | Same as EC-04. |
| EC-06 | Inputs: empty, spaces only, 500 characters, emoji, `<b>`, quotes, Hindi or Telugu text, leading zeros in phone numbers | Clear validation. Text is shown safely (no HTML runs). It's stored and shown the same way. |
| EC-07 | Numbers: 0, negative, decimals, very large, commas | Clear validation. No wrong maths. |
| EC-08 | Dates: past dates, far-future dates, 29 Feb, the day the clocks would change elsewhere | Handled sensibly. Shown in IST. |
| EC-09 | Empty states: new outlet with no menu, no orders, no staff | Helpful empty messages, not errors or blank screens. |
| EC-10 | Large data: menu with 500 items, 100 tables, 1,000 orders in a day | Pages load in a few seconds. Search and filters still work. |
| EC-11 | Slow network (browser developer tools → "Slow 3G") | Loading states show. There's no way to submit twice. |
| EC-12 | Session expiry while a form is half-filled | The user is told. Ideally the input isn't lost silently. |
| EC-13 | Deleting things that are in use: a category with items, a table with an open order, a staff member with open orders | Blocked with a clear reason, or handled safely. |
| EC-14 | Sold-out or price change while a customer or waiter has the item in a cart | Handled clearly at checkout. |
| EC-15 | Exports and downloads with special characters and large date ranges | The file opens correctly in Excel. The numbers match the screen. |
| EC-16 | Notifications (SMS, email, push) | They arrive, once, with the right content and links. |
