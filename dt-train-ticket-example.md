[Back to Main Page](./)

# Train ticket example

Train ticket purchasing requirements:
* If you want to take a train after 9PM you get the ticket at the “Super-Saver“ price. 
* If you want to take a train before 6AM you get the ticket at a “Saver“ price. 
* At other times of the day you pay the standard price. 
* If you have a Railcard you get a 25% rebate for all tickets except “Super Saver”
  
| # | Question | Assumption |
| :-- | :-- | :-- |
| 1 | Does "after 9PM" mean strictly after 21:00 (21:01+) or 21:00 inclusive? | Exclusive — 21:00 is Standard, 21:01+ is Super-Saver |
| 2 | Does "before 6AM" mean strictly before 06:00 (up to 05:59) or 06:00 inclusive? | Exclusive — 05:59 is Saver, 06:00 is Standard |
| 3 | What about trains exactly at midnight (00:00)?  Is this considered "after 9PM" (previous day) or "before 6AM" (new day)? | 23:59 - Super-Saver; 00:00 - Saver |
| 4 | Do the three time ranges cover all 24 hours? Specifically: 06:00–21:00 (Standard), 21:01–23:59 (Super-Saver), 00:00–05:59 (Saver) - is this correct? | Yes |


> Note: If modeled as limited-entry with three separate binary conditions (Is after 9PM? / Is before 6AM? / Is other time?), we'd get 2×2×2×2 = 16 rules, where 10 (62,5%) would be infeasible (a train can only depart in one time range).
> The extended-entry approach with one 3-value condition eliminates this waste: 3×2 = 6 rules, all feasible.

## Legend:
* ~ - any value
* P1 - after 9 PM   (EP+BVA 21:00 | 21:01     23:59 | 00:00 )
* P2 - before 6 AM  (EP+BVA 23:59 | 00:00     05:59 | 06:00 )
* P3 - other time   (EP+BVA 05:59 | 06:00     21:00 | 21:01 ) 
---


## Full Decision Table 
*Number of rule = 3 * 2 = 6*
  
| Conditions              | Parameters | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5 | Rule 6  |
|-------------------------|------------|--------|--------|--------|--------|--------|---------|
| C1: Time                | P1, P2, P3 | P1     | P2     | P3     | P1     | P2     | P3      |
| C2: Railcard presents   | T, F       | T      | T      | T      | F      | F      | F       |
| **Actions**             |            |        |        |        |        |        |         |
| A1: “Super-Saver“ price |            | x      | -      | -      | x      | -      | -       |
| A2: "Saver“ price       |            | -      | x      | -      | -      | x      | -       |
| A3: Standard price      |            | -      | -      | x      | -      | -      | x       |
| A4: 25% rebate          |            | -      | x      | x      | -      | -      | -       |


---

## Traceability Matrix

| Collapsed Rule | Derived from | Actions |
| :-- | :-- | :-- |
| Rule 1 | Full: 1, 4 | A1 |
| Rule 2 | Full: 2 | A2 + A4  |
| Rule 3 | Full: 3  |  A3 + A4|
| Rule 4 | Full: 5 | A2 |
| Rule 5 | Full: 6 | A3 |

---

## Collapsed Decision Table 
  
| Conditions              | Parameters | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5  |
|-------------------------|------------|--------|--------|--------|--------|---------|
| C1: Time                | P1, P2, P3 | P1     | P2     | P3     | P2     | P3      |
| C2: Railcard presents   | T, F       | ~      | T      | T      | F      | F       |
| **Actions**             |            |        |        |        |        |         |
| A1: “Super-Saver“ price |            | x      | -      | -      | -      | -       |
| A2: "Saver“ price       |            | -      | x      | -      | x      | -       |
| A3: Standard price      |            | -      | -      | x      | -      | x       |
| A4: 25% rebate          |            | -      | x      | x      | -      | -       |

---

See also:

* **[Decision Table Testing](./decition-table.md)** -  Practical Example of designing test cases.
* **[Decision Table Template](./template-decision-table.md)**
* **[Decision Table Examples](./decision-table-example.md)** - All practice examples 
* **[Back to Main Page](./)**


