[Back to Main Page](./)

# Tax System

A tax system needs to be updated due to new legislation. For a person with a salary of  less than 20.000 and who is married, the tax needs to be re-calculated.   
If the person also has more than two and less than five children, an additional 10 % reduction is applicable.

| # | Questions to BA, PO, Dev | Answers | 
| :--- | :--- | :---: | 
| **1** | What should be done if a person has exactly 2 or exactly 5 children? (The requirement says "> 2 and < 5", which only covers 3 and 4).  | | 
| **2** | 	Can a person with a salary >= 20,000 get the 10 % reduction if they have 3-4 children, or is the reduction only for married people making < 20,000? Is there true operator AND between Salary and Married | | 


## Full Decition Table
Test cases = 2 * 2 * 2 = 8 (numbers of rules)

| Type | Parameters  | Rule 1 | Rule 2 | Rule 3 | Rule 4 |  Rule 5 | Rule 6 | Rule 7 | Rule 8 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |:---: |:---: |:---: |
| **Salary of less than 20.000?** | T, F                   | T | T | T | T | F | F | F | F |
| **Is married?**   | T, F |                                 T | T | F | F | T | T | F | F |
| **Has more than two and less than five children** ({3, 4})| T, F | T | F |  T | F | T | F | T | F |
| -------------- | ------------- | --- | --- | --- | --- | --- | --- | --- | --- | 
| **Tax needs to be re-calculated** |                       | x | x | - | - | - | - | - | - |
| **An additional 10%** |                                   | x | - | - | - | - | - | - | - |


## Legend:
* True: a salary  <  20.000
* False: a salary  >= 20.000
* ~ - any parameter
---


## Collapsed decision table with "don't care" values

| Type | Parameters  | Rule 1 | Rule 2 | Rule 3 | Rule 4 | 
| :--- | :--- | :---: | :---: | :---: | :---: | 
| **Salary of less than 20.000?** | T, F                   | T | T | T | F |
| **Is married?**   | T, F |                                 T | T | F | ~ |
| **Has more than two and less than five children** | T, F | T | F | ~ | ~ |
| -------------- | -----------------| --- | --- | --- | --- | 
| **Tax needs to be re-calculated** |                       | x | x | - | - | 
| **An additional 10%** |                                   | x | - | - | - | 


---

See also:

* **[Decision Table Testing](./decition-table.md)** -  Practical Example of designing test cases.
* **[Decision Table Template](./template-decision-table.md)**
* **[Decision Table Examples](./decision-table-example.md)** - All practice examples 
* **[Back to Main Page](./)**


