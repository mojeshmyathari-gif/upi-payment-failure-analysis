# UPI Payment Failure Analysis

A business analysis project on why UPI payments fail and what a product team could do about it. It is a personal portfolio project built on a small sample dataset.

## What I did

- Wrote a 10-section Business Requirements Document with 12 functional requirements, prioritised with MoSCoW.
- Drew a 4-lane BPMN swimlane map of the payment flow (customer app, NPCI central switch, remitter bank, beneficiary bank). The map shows 5 ways a payment can fail: invalid PIN, insufficient funds, switch timeout, remitter server down and a beneficiary-side failure.
- Used Excel VLOOKUP to match response codes such as `ZM` to plain-language error descriptions, and SQL (LEFT JOIN, GROUP BY) to summarise transactions by status and bank.
- Built a Power BI model with a one-to-many relationship and a DAX success-rate measure.

## What the dashboard shows

- 15 sample transactions, 14 successful and 1 failed.
- Success rate of 93.33%, from a DAX measure.
- The one failure used code `ZM` (invalid customer UPI PIN), worth INR 1,500 of INR 15,840 in total order value, and it sat on the SBI route.
- Recommendation: an in-app prompt that asks the user to check or reset the UPI PIN before a retry.

## Limits

The sample has only 15 transactions, so the 93.33% rate and the SBI pattern show how the analysis works. They are not a real-world finding.

## Tools

SQL, Excel, Power BI, DAX, BPMN (draw.io)

## Files

- `images/upi-dashboard.png`: the Power BI dashboard
