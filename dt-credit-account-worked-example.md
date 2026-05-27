[Back to Main Page](./)

# Credit account worked example

Let’s look at another example. If you are a new customer opening a credit
account, you will get a 15% discount on all your purchases today. If you are an
existing customer and you hold a loyalty card, you get a 10% discount. If you have
a coupon, you can get 20% off today (but it cannot be used with the new customer
discount). Discount amounts are added, if applicable. 

Notes: 
You can not be both a new customer and already hold a loyalty card.
Process of getting of loyalty card is out of scope for this DT


## Questions & Assumptions

| # | Question | Assumption |
|---|----------|------------|
| 1 | Is it possible for an existing customer to not have a loyalty card? If so, is that customer still eligible to receive a discount when using a coupon?  | Existing customer can be without loyalty card and can receive a discount with coupon |
| 2 | "You can get 20% off today" — does this apply to a single purchase or to all purchases made today? | A single purchase |
| 3 | If the coupon is valid for a single purchase, am I still entitled to use my 15% new customer discount on all other purchases throughout the day? | no logic built into DT  |
| 4 | Are there any limits on the number of coupons per customer? What about limits on the number of coupons that can be used in a single day? | One per person / one per day |
| 5 | Can coupons be combined  with each other? | No | 
| 6 | When a new customer has a coupon, does the system automatically apply the higher discount (20% coupon), or can the customer choose between coupon (20%) and new customer discount (15%)? | System applies the higher discount — coupon 20% replaces the 15% new customer discount |

> Note: The first condition starts with F (existing customer) to align rule numbering between the full and collapsed tables.

## Full Decision Table
Test cases = 2 * 2 * 2 = 8 (numbers of rules)

| Condition                                           | Parameters | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5 | Rule 6 | Rule 7 | Rule 8  |
|-----------------------------------------------------|------------|--------|--------|--------|--------|--------|--------|--------|---------|
| C1: A new customer (T - new, F - existing)              | T, F    |   F   | F      | F      | F      | T      | T      | T      | T       |
| C2: Hold a loyalty card                                 | T, F    |   T   | T      | F      | F      | N/A    | N/A    | F      | F       |
| C3: You have a coupon                                  | T, F     |   T   | F      | T      | F      | T      | F      | T      | F       |
| Action                                     |            |         |       |        |        |        |        |        |        |         |
| A1: Can get a 15% discount on all your purchases today. |         | -     | -      | -      | -      | N/A    | N/A    | -      | x       |
| A2: Can get a 10% discount.                             |         | x     | x      | -      | -      | N/A    | N/A    | -      | -       |
| A3: Can get 20% off today                               |         | x     | -      | x      | -      | N/A    | N/A    | x      | -       |
| A4: No discount (full price)                         |            | -     | -      |  -     |  x     | N/A    | N/A    |  -     | -       |  
| Total discount, %                                   |             | 30    | 10     | 20     | 0      | N/A    | N/A    | 20     | 15      |



## Legend:
* ~ - any parameter
* N/A (in conditions) - this condition causes the infeasibility
* N/A (in actions) - rule is infeasible, no testable outcome

---

## Traceability Matrix

| Collapsed Rule | Derived from | Actions |
| :-- | :-- | :-- |
| Rule 1 | Full: 1 | Use 10% discount loyalty card and 20% coupon|
| Rule 2 | Full: 2 | Use 10 % discount loyalty card |
| Rule 3 | Full: 3, 7 | Use only coupon |
| Rule 4 | Full: 4 | Without any discount|
| Rule 5 | Full: 8 | Use 15 % discount for a new customer|
| N/A | Full: 5, 6 | You can not be both a new customer and already hold a loyalty card. |

## Collapsed Decision Table 

*(Using "don't care" values (~) and Infeasible conditions (N/A))*

  

| Condition                                           | Parameters | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5  |
|-----------------------------------------------------|------------|--------|--------|--------|--------|---------|
| C1: A new customer (T - new, F - existing)          | T, F       | F      | F      | ~      | F      | T       |
| C2: Hold a loyalty card                             | T, F       | T      | T      | F      | F      | F       |
| C3: You have a coupon                               | T, F       | T      | F      | T      | F      | F       |
| **Action**                                              |        |        |        |        |        |         |
| A1: Can get a 15% discount on all your purchases today. |        | -      | -      | -      | -      | x       |
| A2: Can get a 10% discount.                             |        | x      | x      | -      | -      | -       |
| A3: Can get 20% off today                               |        | x      | -      | x      | -      | -       |
| A4: No discount (full price)                        |            | -      | -      | -      | x      |  -      |           
| Total discount, %                                   |            | 30     | 10     | 20     | 0      | 15      |

---



See also:

* **[Decision Table Testing](./decition-table.md)** -  Practical Example of designing test cases.
* **[Decision Table Template](./template-decision-table.md)**
* **[Decision Table Examples](./decision-table-example.md)** - All practice examples 
* **[Back to Main Page](./)**
