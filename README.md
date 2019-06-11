# Loan Repayment Calculator Lab

**$, €, ₠, ¢, ¥, £, ₵, ₡, ₳, ฿, ₢, ₫, ৳, ₯, ₣, ₲, ₴, ₭, ₥, ₦, ₧, ₱, ₰, ₹, ₨, ₪, ₮, ₩, ₽, ؋, ﷼**

How do banks figure out how long it will take for a client to pay back a loan? In general, banks have a set of instructions (an algorithm) that takes in important information like amount borrowed, bank fees, and interest rates to figure out how long a client will need to pay back the full loan plus fees and interest.

In this lab, you'll be writing Python methods to calculate how long it will take someone to pay back a loan.

> Although banks usually compound interest monthly, we're going to assume interest is compounded once at the beginning of the loan period.

Take a look at this chart, which provides the most recent criteria and fees for loan services.

| Loan Type | Interest Rate | Min. Monthly Payment (USD) | Bank Fee (USD) | Min. Loan (USD) | Max. Loan (USD) |
| --- | :---: | :---: | :---: | :---: | :---: |
| EZ Loan | 18.5% | $50 | $0 | $100 | $40,000 |
| High-Interest | 12.5% | $200 | $0 | $200 | $100,000 |
| Medium-Interest | 7.5% | $350 | $300 | $600 | $30,000 |
| Low-Interest | 3% | $300 | $500 | $1,000 | $10,000 |

> Note: the bank calculates interest-adjusted amounts *before* it assesses fees.

## Instructions

1) Create a function called `simple_payment` that only accepts `monthly payment` and returns the number of months it will take to repay a $3,000 zero-interest, zero-fee loan.

**Example:** When I run `simple_payment(300)` for $300/month, it should return **10** because it would take 10 months to pay back $3,000 by paying $300 per month.

2) Create a function called `repay_low_interest` that takes in a `loan amount` and a `monthly payment`. It should integrate the bank's fee and the interest rate to return the number of months it would take to repay that loan.

**Example:** For a Low-Interest loan of $5,000 paying back $300/month: `repay_low_interest(5000, 300)` should return **19**. (Interest adjusted amount: 1.03 * 5000 = 5150. With 500 in bank fees, the total is 5650. 5650/300 = 18.833, rounded up is 19.)

*Bonus*: if the `loan amount` is outside the bank's acceptable loan range, suggest the user `Borrow a different amount`.

3) Create a more flexible fare calculator method called `repay_calculator` that takes in the `loan amount`, `monthly payment`, and `loan type` and returns the number of months it would rake to repay that loan.

**Example:** For a $9,000 Medium-Interest loan paid back at $500/month, `repay_calculator(9000, 500, "medium")` should return **20**. (Interest adjusted amount: 1.075 * 9000 = 9675. With 300 in bank fees, the total is 9975. 9975/500 = 19.95, rounded up is 20.)

*Bonus:* if no loan type is given, have `repay_calculator` default to Medium-Interest.

*Double-Bonus:* if the `loan amount` is outside the bank's acceptable loan range, suggest the user `Borrow a different amount`.

**Advanced Bonus Challenge:**

4) Which loan type is best? Create a method `best_loan` that accepts the `loan amount` and `monthly payment`, and returns which loan type will cost the borrower the least along with the cost to the borrower to take that type of loan. This is an open ended one - there are many ways to do this!

Keep in mind that for some loan amounts, some loans cannot be used.

*Bonus:* is "EZ Loan" ever the best kind of loan? Under what circumstances is it better than the other options?

**Double Advanced Bonus Challenge:**

5) What if instead of assessing interest at the beginning of the loan period, the interest is (more-realistically) assessed monthly? Create a new `repay` method that adds interest at the end of each month. Assume good behavior by the loan recipient who pays back the expected amount before the interest is assessed on the remaining balance.

**Example:** a Medium-Interest loan of $3,000 paid back at $300/month would take **21** months to pay back, but a Medium-Interest loan of $9,000 paid back at $500/month would never get paid back.

*Bonus:* How does `repay` (assessing monthly interest) compare to `repay_calculator` (assessing one-time interest)?

*Double-Bonus:* Use the same idea of assessing monthly interest to write a new `best` method that returns which loan type will cost the borrower the least (including monthly interest and bank fees) along with the cost to the borrower to take that type of loan.
