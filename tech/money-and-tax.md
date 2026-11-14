# Money and tax checklist

Keep a calculator or spreadsheet open. Work out every expected total yourself before looking at the screen. Any difference, even ₹0.01, is a P0 bug.

| ID | Check | Pass when |
|---|---|---|
| MT-01 | GST on an item priced **excluding** tax (e.g. ₹100 + 5%) | Tax and total are exactly right. CGST and SGST are split correctly on the bill. |
| MT-02 | GST on an item priced **including** tax | The base and tax amounts are worked out correctly and the total doesn't change. |
| MT-03 | Items with different tax rates on one bill | Each rate is shown and added up separately. |
| MT-04 | Prices with paise (₹99.50) × odd quantities (3, 7) | No rounding drift. The bill total rounds the way the settings say. |
| MT-05 | Round-off line | The round-off amount is correct and shown. |
| MT-06 | Service charge on and off | It's applied on the right base. Tax on it follows the rule. It can be waived only with permission. |
| MT-07 | Percentage discount and flat discount | It's applied before tax as the rule says. Tax is recalculated. |
| MT-08 | Discount bigger than the bill | Refused, or capped at zero. Never a negative bill. |
| MT-09 | Zero-value bill (100% discount or a complimentary order) | It can be settled. It shows correctly in reports. |
| MT-10 | Split equally into 3 parts on a total that doesn't divide evenly (₹100) | The parts add up to exactly ₹100. |
| MT-11 | Split by items, and split across two payment methods | Each part is right. The payment methods add up to the total. |
| MT-12 | Tip, if supported | Recorded separately from sales and tax. |
| MT-13 | Partial refund or credit note | Tax is reversed in proportion. The original bill stays unchanged and linked. |
| MT-14 | Refund more than was paid | Refused. |
| MT-15 | Invoice numbers across a day, two tills, and day-end | Continuous, with no gaps or repeats. They reset or continue as the settings say. |
| MT-16 | Day-end totals | Sales = sum of bills. Payments by method = sum of payments. Cash expected = float + cash sales − cash out + cash in. |
| MT-17 | Analytics vs bills | Gross, net, tax and discount totals in Analytics match the bills for the same dates. |
| MT-18 | Large order (50 items, ₹1,00,000+) | Totals are right. Amounts are formatted in Indian style. Nothing overflows. |
| MT-19 | Price change while an order is open | The rule is clear and consistent: old price or new price. |
