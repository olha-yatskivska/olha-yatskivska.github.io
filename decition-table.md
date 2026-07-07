[Back to Main Page](./)

# Decision Table

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)


## Applicability

Decision tables are a good way to record complex business rules that a system must implement.
1. This technique is particularly useful when the test object is specified in the form of flowcharts or tables of business rules.
2. Decision tables are also a requirements definition/review technique

## Table Structure 
[Template Decision Table](./template-decision-table.md)

| Type | Parameters  | Rule 1 | Rule 2 | ... | Rule p | 
| ----| :--- | :---: | :---: | :---: | :---: | 
| Condition 1 | T, F | T  | T | T | F | 
| Condition 2   | T, F | T | T | F | F |
| ....  | T, F | T | F | T | F |
| Condition m | T, F | T | T | F | F |
| **Actions** | -----------------| --- | --- | --- | --- | 
| Action 1 |  | x | x | - | - | 
| Action 2 |   | x | - | x | - | 
| .... |       | x | - | - | - | 
| Action  n |  | x | - | x | - | 


>  * Conditions 1 through m represent various input conditions.
>  * Actions 1 through n are the action that should be taken depending on the various combinations.
>  * Each of the rules defines a unique combination of conditions that result in the execution of the actions associated with that rule. 

----

* The actions do not depend on the order in which the conditions are evaluated, but only on their values (all values are assumed to be available simultaneously) 
* Actions depend only on the specified conditions, not on any previous input conditions or system state
* Each rule becomes a test case
* The Conditions specify the inputs and the Actions specify the expected results.
* Conditions can be  binary ({Yes, No}; {True, False}) or more complex ({10-100; 100-1000}; {<5, 6 or 7; 25 <= x <= 65}) - combinations with EP technique.
* If the rule's conditions are binary, a single test for each combination is probably sufficient.
* If a condition is a range of values, consider testing at both the low and high end of the range - combination with BVA technique.
* Note: In practice BVA better check by separate test cases 

---

## DT creation Steps

1. Identify and wright down all Conditions, analyse Parameters
2. Count a maximum number of Parameter’s Combinations (multiply them)
3. Fill out the combinations in table (Rules): Start with the total number of rules. For each condition, divide the previous block size by 2 and alternate T/F in blocks of that size. (See example)[]
4. Wright down the Actions
5. To Collapse table exclude redundant columns (Tests\Rules) (two rules that share the same action outcome and differ only in conditions that don't affect that outcome)

---

## Decision Table Composition: Tips & Tricks

* **List all Conditions and their combinations:** Ensure every logical variable is identified before mapping the outcomes.
* **Group related conditions together:** Keep dependent or logically connected conditions in adjacent rows to make the table easier to follow.
* **Place the most dominant conditions at the top:** Start with the "high-level" rules that have the biggest impact on the final result.
* **Position multi-value conditions at the bottom:** If a condition has three or more possible values (e.g., "Payment Method: Card, Cash, PayPal, Gift Card"), place it lower in the table to keep the binary (Yes/No) logic clear at the top.
* **Decompose overly complex tables:** If a table becomes too large or difficult to read, break it down into several smaller, simpler tables.

---

## Limitations/Difficulties
When considering combinations of conditions, finding all the interacting conditions can be challenging, particularly when requirements are not well-defined or do not exist. 
Care must be taken when selecting the conditions considered in a decision table so that the number of combinations of those conditions remains manageable. In the worst case, the number of rules will grow exponentially

---
 
## Coverage
The coverage is measured as a percentage of the number of rules covered by the test suite and the total number of feasible rules:  
```Coverage = (Number of rules tested / Total number of feasible rules) × 100%```
Coverage Types:
* full decision table coverage
* collapsed decision table coverage
* analytical decision table coverage - add info 

---

See also:


* **[Decision Table Testing](./decision-table-example.md)** -  Practical Example of designing test cases.
* **[Back to Main Page](./)**






