[Back to Main Page](./)

# Good Health example

The insurance company GoodHealth has launched a new health insurance product - for all customers both new and existing - with the following specification:
* Standard premium fee is 500€.
* A bonus program offers customers buying the health insurance product with a 25€ discount to the standard premium fee to accept participating in the medical tests even if they are not participating.
* The customers get a 25€ discount to the standard premium for each one of four medical tests (BMI, blood pressure, glucose, and cholesterol) that they take as part of the yearly medical test plus an extra 75€ if they take all the tests.

| # | Question | Assumption |
| :-- | :-- | :-- |
| 1 | Can a customer accept participation but take zero tests? Do they still receive the 25 € acceptance discount? | Yes - Rule 16 / Collapsed Rule 5 covers this |
| 2 | Can a customer take medical tests without accepting the bonus program participation? | No - acceptance is a prerequisite |
| 3 | Is the "all four tests" bonus (75€) applied automatically, or does the customer need to complete them in the same visit/period? | Automatically upon completion of all four |



## Non-collapsed decision table but with the limitation
Test cases = 2 * 2 * 2 * 2 * 2 = 32 (numbers of rules)
> Note: When C1=F (customer declines participation), all 16 combinations produce the same outcome: 0€ discount, all other conditions N/A. Instead of enumerating 32 rules, we show 16 (C1=T) + 1 consolidated rule (C1=F) = 17 rows, cutting the table nearly in half. 
 
| Conditions                                     | Parameters | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5 | Rule 6 | Rule 7 | Rule 8 | Rule 9 | Rule 10 | Rule 11 | Rule 12 | Rule 13 | Rule 14 | Rule 15 | Rule 16 | Rule  17  |
|------------------------------------------------|------------|--------|--------|--------|--------|--------|--------|--------|--------|--------|---------|---------|---------|---------|---------|---------|---------|-----------|
| C1: Accept participating in the medical tests  | T, F       | T      | T      | T      | T      | T      | T      | T      | T      | T      | T       | T       | T       | T       | T       | T       | T       | F         |
| C2: BMI                                        | T, F       | T      | T      | T      | T      | T      | T      | T      | T      | F      | F       | F       | F       | F       | F       | F       | F       | N/A       |
| C3: Blood pressure                             | T, F       | T      | T      | T      | T      | F      | F      | F      | F      | T      | T       | T       | T       | F       | F       | F       | F       | N/A       |
| C4: Glucose                                    | T, F       | T      | T      | F      | F      | T      | T      | F      | F      | T      | T       | F       | F       | T       | T       | F       | F       | N/A       |
| C5: Cholesterol                                | T, F       | T      | F      | T      | F      | T      | F      | T      | F      | T      | F       | T       | F       | T       | F       | T       | F       | N/A       |
| **Actions**                                    |            |        |        |        |        |        |        |        |        |        |         |         |         |         |         |         |         |           |
| Tests taken                                    |            | 4      | 3      | 3      | 2      | 3      | 2      | 2      | 1      | 3      | 2       | 2       | 1       | 2       | 1       | 1       | 0       |                        
| A1: Discount, €                                |            | 200    | 100    | 100    | 75     | 100    | 75     | 75     | 50     | 100    | 75      | 75      | 50      | 75      | 50      | 50      | 25      |          |

---

## Traceability Matrix

| Collapsed Rule | Derived from | Actions |
| :-- | :-- | :-- |
| Rule 1 | Full: 1 | All tests taken |
| Rule 2 | Full: 2, 3, 5, 9 | Any 3 of 4 tests taken — 4 combinations |
| Rule 3 | Full: 4, 6, 7, 10, 11, 13 | Any 2 of 4 tests taken — 6 combinations |
| Rule 4 | Full: 8, 12, 14, 15 | Any 1 of 4 tests taken — 4 combinations |
| Rule 5 | Full: 16 | Accept participation, but doesn't participate |
| Rule 6 | Full: 17-32 | The customer doesn't accept participation |

## Collapsed Decision Table 
  
| Conditions                                     | Parameters | Rule 1 | Rule 2 | Rule 3 | Rule 4  | Rule 5 | Rule 6  |
|------------------------------------------------|------------|--------|--------|--------|---------|--------|---------|
| C1: Accept participating in the medical tests  | T, F       | T      | T      | T      | T       | T      | F       |
| C2: BMI                                        | T, F       | T      | T/F    | T/F    | T/F     | F      | N/A     |
| C3: Blood pressure                             | T, F       | T      | T/F    | T/F    | T/F     | F      | N/A     |
| C4: Glucose                                    | T, F       | T      | T/F    | T/F    | T/F     | F      | N/A     |
| C5: Cholesterol                                | T, F       | T      | T/F    | T/F    | T/F     | F      | N/A     |
| **Actions**                                    |            |        |        |        |         |        |         |
| Tests taken                                    |            | 4      | 3      | 2      | 1       |  0     | N/A     |
| A1: Discount,  €                               |            | 200    | 100    | 75     | 50      | 25     | 0       |

## Legend:
* T/F - any combination of True and False in combinations with required Number of True parameters for C2-C5
* N/A  - not applicable

---

See also:

* **[Decision Table Testing](./decition-table.md)** -  Practical Example of designing test cases.
* **[Decision Table Template](./template-decision-table.md)**
* **[Decision Table Examples](./decision-table-example.md)** - All practice examples 
* **[Back to Main Page](./)**


