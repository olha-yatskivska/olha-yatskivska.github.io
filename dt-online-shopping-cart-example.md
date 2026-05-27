[Back to Main Page](./)

# Online Shopping Cart Checkout

You are testing the checkout process of an online shopping cart system.   
There are regular customers and premium customers, which have a special discounts.    
There are three options of payment method: Credit card, PayPal and Gift card.    
Regular customers can order only products that are in stock now, in other case there should be the validation.   
If Customer has Premium account, there is an option to make pre-order for products out of stock.    
Gift card payment method is allowed to be used for all users but only for products that are in stock.

**Customer Type:**
* Regular customer (T)
* Premium customer (F)

**Product Availability:**
* Product is in stock (T)
* Product is out of stock (F)

**Payment Method:**
* Credit card (a)
* PayPal (b)
* Gift card (c)

**Actions:**
* Action1 : Display a notification about the product being out of stock and pre-order mode
* Action2 : Inform the customer about the unavailability of the product
* Action3 : Show customer the additional field for a Gift Card payment method
* Action4 : Block the Gift card field and prompt the customer to select an alternative payment method
* Action5 : Process the order
---

## Questions & Assumptions

| # | Question | Assumption |
|---|----------|------------|
| 1 | When does a Regular customer transition to a Premium customer? (Could you also confirm if my understanding is correct: does 'Regular' refer to an unregistered guest user, while 'Premium' refers to a registered account holder?)  | Regular customer - unregistered guest user; Premium - registered account holder |
| 2 | Does 'Action 5: Process the order' include a pre-order mode? Or is this action triggered only when the product is currently in stock? | Include a pre-order mode |
| 3 | Regular customers can order only products that are in stock now, in other case there should be the validation.* - What exactly does 'validation' mean? Is it simply Action 2 (inform about unavailability), or is there a separate validation flow (e.g., waitlist registration, email notification when back in stock)? | There is no additional Action for validation |
| 4 | Should Action 3 (show gift card field) only appear when the gift card can actually be used (product in stock)? Or does the field always appear and then gets blocked by Action 4 when not applicable? | The addition field for a Gift Card payment method appears after selecting this payment method |
| 5 | The requirements mention that Premium customers have "special discounts." However, there is no Action defined for applying a discount. How and when is this discount applied to the cart? | Out of current DT scope until clarified; may require an additional action and condition | 
| 6 | *Regular customers can order only products that are in stock now* - Does system block order before payment selection is reachable for that case? | Yes, it does |


## Out of Scope (noted for discussion)

| # | Question | Why noted |
|---|----------|-----------|
| 1 | How should the system behave if the order total is either greater or less than the Gift Card balance? For example, if the balance is insufficient, does the system allow a split payment with PayPal? If the balance is greater, does the remainder stay on the card? | Maybe need it's own DT |
| 2 | Could you clarify what is included in the 'Process the order' action? For example, does it involve: <br> The 'Place Order' button becoming active? <br> Triggering a confirmation email to the customer? <br> An automatic deduction from the inventory (stock count)? <br>  | UX |


## Full Decision Table
Test cases = 2 * 2 * 3 = 12 (numbers of rules)

| Conditions | Parameters | Rule 1 |Rule 2 | Rule 3 | Rule 4 | Rule 5 | Rule 6 | Rule 7 | Rule 8 | Rule 9 | Rule 10 | Rule 11 | Rule 12 |
|-----------------------|------------|--------|-------|--------|--------|--------|--------|--------|--------|--------|---------|---------|---------|
| Regular customer | T, F   |   T    |   T   |   T    |    T   |    T   |    T   |    F   |    F   |   F    |    F    |    F    |    F    |
| Product is in stock                                                                       | T, F       |   T    |   T   |   T    |    F   |    F   |    F   |    T   |    T   |   T    |    F    |    F    |    F    |
| Payment Method:                                                                           | a, b,c     |   a    |   b   |   c    |   N/A  |   N/A  |   N/A  |    a   |    b   |   c    |    a    |    b    |    c    |
| **Actions**                                                                               |            |        |       |        |        |        |        |        |        |        |         |         |         |
| Display a notification about the product being out of stock and pre-order mode            |            |   -    |   -   |   -    |    -   |    -   |    -   |    -   |    -   |   -    |    x    |    x    |    x    |
| Inform the customer about the unavailability of the product                               |            |   -    |   -   |   -    |    x   |    x   |    x   |    -   |    -   |   -    |    -    |    -    |    -    |
| Show customer the additional field for a Gift Card payment method                         |            |   -    |   -   |   x    |    -   |    -   |    -   |    -   |    -   |   x    |    -    |    -    |    -    |
| Block the Gift card field and prompt the customer to select an alternative payment method |            |   -    |   -   |   -    |    -   |    -   |    -   |    -   |    -   |   -    |    -    |    -    |    x    |
| Process the order                                                                         |            |   x    |   x   |   x    |    -   |    -   |    -   |    x   |    x   |   x    |    x    |    x    |    -    |


## Legend:
* ~ - any parameter
* N/A - not applicable conditions
* a/b - either parameter leads to the same outcome

---

NOTE: Although payment methods a and b are collapsed into a single rule, separate test cases should still be created for each payment method to ensure complete coverage."
---

## Traceability Matrix

| Collapsed Rule | Derived from | Actions |
| :-- | :-- | :-- |
| Rule 1 | Full: 1, 2, 7, 8 | Process order |
| Rule 2 | Full: 3, 9 | Show gift card + Process |
| Rule 3 | Full: 4, 5, 6 | Inform unavailability |
| Rule 4 | Full: 10, 11 | Pre-order + Process |
| Rule 5 | Full: 12 | Pre-order + Block gift card |

---
## Collapsed Decision Table 

*(Using "don't care" values (~) and not applicable conditions (N/A))*

| Conditions                                                                                | Parameters |  Rule 1 | Rule 2 | Rule 3 |  Rule 4 |  Rule 5 |
|-------------------------------------------------------------------------------------------|------------|---------|--------|--------|----------|--------|
| Regular customer                                                                          | T, F       | ~       | ~      | T      |     F    |    F   |
| Product is in stock                                                                       | T, F       |    T    |   T    |    F   |     F    |    F   |
| Payment Method:                                                                           | a, b, c    |   a/b   |   c    |   N/A  |    a/b   |    c   |
| **Actions**                                                                               |            |         |        |        |          |        |
| Display a notification about the product being out of stock and pre-order mode            |            |   -     |   -    |    -   |     x    |    x   |
| Inform the customer about the unavailability of the product                               |            |   -     |   -    |    x   |     -    |    -   |
| Show customer the additional field for a Gift Card payment method                         |            |   -     |   x    |    -   |     -    |    -   |
| Block the Gift card field and prompt the customer to select an alternative payment method |            |   -     |   -    |    -   |     -    |    x   |
| Process the order                                                                         |            |   x     |   x    |    -   |     x    |    -   | 

---

See also:

* **[Decision Table Testing](./decition-table.md)** -  Practical Example of designing test cases.
* **[Decision Table Template](./template-decision-table.md)**
* **[Decision Table Examples](./decision-table-example.md)** - All practice examples 
* **[Back to Main Page](./)**





