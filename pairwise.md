[Back to Main Page](./)

# Pairwise Testing

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus (ISTQB)
> * ISTQB Advanced Test Analyst Course [Instractor: Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)
> * A Practitioner's Guide to Software Test Design by Lee Copeland
> * Satisfice Methodology (James Bach) - [satisfice.com](https://www.satisfice.com/)


* Pairwise testing is used when testing software in which several input parameters, each with several possible values, must be tested in combination, giving rise to more combinations than are feasible to test in the time allowed.
  
> *Example from Lee Copeland "A Practitioner's Guide to Software Test Design":*
>  * *If a system had four different input parameters and each one could take on one of  three different values, the number of combinations is **3⁴**, which is **81**. It is possible to cover all the pairwise input combinations in only **9 tests** (3x3 - the two largest parameters) - 88 percent reduction in the number of test cases.*
>  * *If a system had thirteen different input parameters and each one could take on one of three different values, the number of combinations is **3¹³**, which is **1 594 323**. It is possible to cover all the pairwise input combinations in only **15 tests** - almost 99,99 percent reduction in the number of test cases.*


> ***Notice that while "All Combinations" grows exponentially, Pairwise grows logarithmically.***

* The input parameters may be independent in the sense that any option for any factor can be combined with any option for any other factor, however, it is not always the case ([PICT](https://github.com/Microsoft/pict/blob/main/doc/pict.md)). 

* The combination of a specific parameter (variable or factor) with a specific value of that parameter is called a parameter-value pair.

* Pairwise testing uses combinatorial techniques to ensure that each parameter-value pair gets tested once against each parameter-value pair of each other parameter, while avoiding testing all combinations of parameter-value pairs.

---

## Manual Approach (Often using Orthogonal Arrays)

> *Orthogonal Arrays: These are fixed tables derived from combinatorial designs. They are "perfectly balanced," meaning every pair appears exactly the same number of times.* 

* A table is constructed with test cases represented by rows and one column for each parameter.
* The Test Analyst then populates the table with values such that all pairs of values can be identified in the table.
* Any entries in the table which are left blank can be filled with values by the Test Analyst using their own domain knowledge.
* If highly risky combinations exist, then add additional test cases to minimize the risk of missing an important combination (Lee Copeland). 

---

## Pairwise Tools (Often use Greedy Algorithms (AllPairs, PICT))

> See more information about [tools](./pairwise-tools.md) and [practical example spreadsheets](https://docs.google.com/spreadsheets/d/1iwLri_iummO5VbK9NMeDdRIPQQAvaEdBTxWiUUDPObo/edit?usp=sharing)

* The tools require, as input, a list of the parameters and their values and generate a suitable set of combinations of values from each parameter that covers all pairs of parameter-value pairs. 

> *Greedy Algorithms (AllPairs, PICT): These tools do not care about balance; they only care about coverage. The algorithm follows a simple logic:*
> 1. Generate a list of all required pairs.
> 2. Create a test case (row) that covers the highest possible number of new pairs.
> 3. Repeat until the "uncovered" list is empty.*

* The output of the tool can be used as input for test cases. Note that the Test Analyst must supply the expected results for each combination that is created by the tools.

* Classification trees are often used in conjunction with pairwise testing. Classification tree design is supported by tools and enables combinations of parameters and their values to be visualized (some tools offer a pairwise enhancement).
This helps to identify the following information:
  * Inputs to be used by the pairwise test technique.
  * Particular combinations of interest (e.g., frequently used or a common source of defects)
  * Particular combinations which are incompatible. This does not assume that the combined factors won’t affect each other; they very well might, but they should affect each other in acceptable ways.
  * Logical relationships between variables. For example, “if variable 1 = x, then variable 2 cannot be y”. Classification trees which capture these relationships are called “feature models”.

---

## Applicability

* The problem of having too many combinations of parameter values manifests itself in at least two different situations related to testing. In both these situations, pairwise testing can be used to identify a subset of combinations that is manageable and feasible:
   * Some test items involve several parameters, each with a number of possible values, for instance a screen with several input fields. 
   * In this case, combinations of parameter values make up the input data for the test cases. Furthermore, some systems may be configurable in a number of dimensions, resulting in a potentially large configuration space. 

* This technique is often used in configuration testing to reduce the number of configurations under test to a manageable number.

* For parameters with many values, equivalence partitioning, or some other selection mechanism may first be applied to each parameter individually to reduce the number of values for each parameter, before pairwise testing is applied to reduce the set of resulting combinations.
  
* Capturing the parameters and their values in a classification tree supports this activity.
  
* These techniques are usually applied to the component integration, system and system integration test levels.

> *You can read more about James Bach's pairwise tool AllPairs in Lesson 54, "The Classification of a Technique Depends on How You Think About It," specifically the section "How to Do Combination Testing Using the All-Pairs Technique."*

---

## Limitations/Difficulties

* There is the **assumption** that the results of a few tests are representative of all tests and that those few tests represent expected usage (in the area of medical devices under study, 66% of failures were triggered by a single variable and 97% by either one variable or two variables interaction).
* If there is an unexpected interaction between certain variables, it may go undetected with this test technique if that particular combination is not tested. 
* There is a **residual risk** that pairwise testing may not detect system failures where three or more variables interact.
* Identifying the parameters and their respective values is sometimes difficult to achieve. Therefore, this task should be performed with the support of classification trees where possible.
* Finding a minimal set of combinations to satisfy a certain level of coverage is difficult to do manually. Tools may be used to find the smallest possible set of combinations.
* Some tools support the ability to force some combinations to be included in or excluded from the final selection of combinations. A Test Analyst may use this capability to emphasize or de-emphasize factors based on domain knowledge or product usage information.
* The traditional pairwise algorithm does not natively handle dependencies between parameters or "forbidden" (invalid) combinations. Modern tools, such as [PICT](https://github.com/Microsoft/pict/blob/main/doc/pict.md), offer extended capabilities to manage these constraints and conditional logic effectively.
* The technique may overlook critical logic paths when dealing with a high volume of True/False values, as simple 2-way coverage is often insufficient for complex boolean logic.

---

## Coverage

The 100% pairwise coverage requires that every pair of values of any pair of parameters be included in at least one combination.

---

## Types of Defects
The most common types of defects found with this test technique are defects related to the combined values of two parameters:
* single-mode faults (problems/bugs).
* double-mode faults

> Note: This technique can't guarantee finding multiple-mode faults

---

## Seven Factors that strongly influence the outcome of your pairwise testing by [James Bach](https://www.satisfice.com/download/pairwise-testing-a-best-practice-that-isnt) : 
1) The actual interdependencies among variables in the product under test. 
2) The probability of any given combination of variables occurring in the field. 
3) The severity of any given problem that may be triggered by a particular combination of 
variables.
4) The particular variables you decide to combine. 
5) The particular values of each variable you decide to test with. 
6) The combinations of values you actually test. 
7) Your ability to detect a problem if it occurs. 

---

See also:

* **[Pairwise Testing Tools Comparison](https://docs.google.com/spreadsheets/d/1iwLri_iummO5VbK9NMeDdRIPQQAvaEdBTxWiUUDPObo/edit?usp=sharing)** - Practical Example Spreadsheets.
* **[Pairwise Testing Tools](./pairwise-tools.md)** - Collection of Online, Desktop and Console Tools
* **[Classification Tree Technique](./classification-tree.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Back to Main Page](./)**

