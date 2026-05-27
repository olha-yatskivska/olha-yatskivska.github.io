[Back to Main Page](./)

# Bicycle rental SRM

Your favorite bicycle daily rental store has just introduced a new Customer Relationship Management system and asked you, one of their most loyal members, to test it. The implemented features are as follows:

●  Anyone can rent a bicycle, but members receive a 20% discount    
●  However, if the return deadline is missed, the discount is no longer available  
●  After 15 rentals, members get a gift: a T-Shirt

---

## Questions & Assumptions

| # | Questions to BA, PO, Dev | Assumption | 
| :--- | :--- | :---: | 
| **1** | *After 15 rentals* - Does this mean they get the shirt exactly on the 15th rental, or after every 15 rentals (15th, 30th, 45th)?  | Yes, exactly once, on the 15th rental  | 
| **2** | Are rentals where the customer missed the return deadline still counted towards the total rentals? |  Yes, they still count as a completed rental  | 
| **3** | Temporary or permanent discount loss? | This rental only | 
| **4** | Does missed deadline affect the T-shirt too? |  No, only discount  | 

## Out of Scope (noted for discussion)

| # | Questions | Why noted  | 
| :--- | :--- | :---: | 
| **1** |  Is there any penalty for a non-member who misses the return deadline? The requirements only mention members losing their discount | Not in requirements but affects UX |
| **2** | Does the system use prepayment or postpayment? If it is prepayment, the 20% discount is applied before the rental.  | Impacts how discount revocation works technically |


---

## Full Decision Table
Test cases = 2 * 2 * 2 = 8 (numbers of rules)

| Conditions             | Parameters | Rule 1 | Rule 2 | Rule 3 | Rule  4 | Rule 5 | Rule 6 | Rule 7 | Rule 8  |
|------------------------|------------|--------|--------|--------|---------|--------|--------|--------|---------|
| Is a Member?           | T, F       | T      | T      | T      | T       | F      | F      | F      | F       |
| Is deadline  missed?   | T, F       | T      | T      | F      | F       | N/A     | N/A   | N/A   | N/A       |
| Is it 15th rental?     | T, F       | T      | F      | T      | F       | N/A     | N/A   | N/A      | N/A       |
| **Actions**            |            |        |        |        |         |        |        |        |         |
| Rent at full price     |            | -      | -      | -      | -       | x      | x      | x      | x       |
| 20% discount           |            | -      | -      | x      | x       | -      | -      | -      | -       |
| Get a gift: a T-Shirt |            | x      | -      | x      | -       | -      | -      | -      | -       |


## Collapsed Decision Table 

*(Using not applicable conditions (N/A))*
 

| Conditions             | Parameters | Rule  1 | Rule 2 | Rule  3 | Rule  4 | Rule 5  |
|------------------------|------------|---------|--------|---------|---------|---------|
| Is a Member?           | T, F       | T       | T      | T       | T       | F       |
| Is deadline  missed?   | T, F       | T       | T      | F       | F       | N/A      |
| Is it 15th rental?     | T, F       | T       | F      | T       | F       | N/A      |
| **Actions**            |            |         |        |         |         |         |
| Rent at full price     |            | -       | -      | -       | -       | x       |
| 20% discount           |            | -       | -      | x       | x       | -       |
| Get a gift: a T-Shirt |            | x       | -      | x       | -       | -       |


---

See also:

* **[Decision Table Testing](./decition-table.md)** -  Practical Example of designing test cases.
* **[Decision Table Template](./template-decision-table.md)**
* **[Decision Table Examples](./decision-table-example.md)** - All practice examples 
* **[Back to Main Page](./)**

