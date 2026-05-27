[(Back to Main Page)](./)

# Equivalence Partitioning (EP)

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)

EP is a technique used to reduce the number of test cases required to effectively test the handling of inputs, outputs, internal values and time-related values  

What does really this technique check? - Assumption!
This is the belief that if one value in a partition works (or fails), all other values in that same partition will behave exactly the same way.

---

* **The Conceptual Definition:** The system handles all members of a specific subset identically. Therefore, a single test case represents the entire partition's behavior.
* **The Risk-Focused Approach:** Any underlying logic flaws that affect only specific values within a partition (and not the representative sample) remain a residual risk. Its reliability depends on how correctly the 'equivalence' is identified during analysis.
* **Mitigation:** Combine EP with Boundary Value Analysis (BVA) to catch edge cases and defects at the boundaries between equivalence partitions


## Advantages
* Number of test cases is reduced.
* Focusing on smaller data-sets to increases the likelihood of detecting defects.
* Allows coverage of large input domains with fewer test cases
* Helps identify missing requirements or ambiguities in specifications.

---

## Limitations
* Equivalence partitioning usually does not consider the boundary conditions.
* Testers may incorrectly assume that all values in a partition behave identically.
* EP may not detect defects related to specific values (e.g., magic numbers, special cases) within a partition.
* If the assumption is incorrect and the values in the partition are not handled in exactly the same way , this technique may miss defect.
* There can be a lot of classes for every entity and its characteristics
* The Test Analyst should have deep domain knowledge  for taking into account possible dependencies between equivalence partitions of different parameters.

> Example of domain knowledge required:
> * Time values: Must recognize that 24-hour cycle resets 
> * Dates: Must recognize database limitations (e.g., 1753 start date in SQL Server)
> * Dependencies: "Valid time" partition depends on "Valid date" partition

---

## Practical Extensions of Equivalence Partitioning (EP)
> [🔗 Practice reference](./ep-templates-nbr.md)
* Volume: Partitioning data sizes into 'low,' 'standard,' and 'stress' loads.
* Security: Grouping user roles based on access level equivalence.
* Localization: Classifying regions with identical character sets or currency formats.
* Interoperability: Browser or OS versions.

---

## Equivalence Class Partitioning
* Based on conditions of inputs / ER
* Both valid and invalid input classes
* One test per one class
* More than one test per one class does not increase EP coverage, but may increase confidence for high-risk partitions (security, financial domains) 
 
---

##  EP types
* Simple (Boolean (True, False), x > 5,  A = B) / Compound (combinations like (x > 5) and (y < 10)) 
* Ordered (rainbow)/ Unordered (colours)
* Open intervals: ( 100 ; +∞ ) / Closed intervals: [ 10 ; 100 ] /Half-open: ( 5 ; 10 ] or [ 5 ; 10 )
* Valid / Invalid / Special values / Non‑existent values (null, empty, missing)
* Discrete (display sizes: 13", 15", 17")/ Continuous (range [0.1 ... 30.0])
* Infinite / Finite
* Singleton Partitioning (Zero (0, Null, N/A, Empty))

---

## Coverage
* Coverage is determined by taking the number of partitions for which a value has been tested and dividing that number by the number of partitions that have been identified.
* Coverage = (Number of partitions with ≥1 test case) / (Total partitions identified) × 100%
* Minimum = Maximum = Acceptable = "Highest" = 1-Wise Coverage (each partition is covered at least once.)
* Using multiple values for a single partition does not increase the coverage percentage.
* EP is strongest when used in combination with boundary value analysis.
* Differentiating between combinations containing only valid partitions and combinations containing one or more invalid partitions is therefore essential
* Invalid equivalence partitions should be tested at least individually, i.e. in combination with valid partitions for the other parameters, in order to avoid defect masking


> ⚠️ **Defect Masking Prevention:**
> * Test invalid partitions SEPARATELY or in combination with valid partitions
> * Example: If parameter A is invalid AND parameter B is invalid, a defect in handling A might be masked by the error from B
> * Rule: Maximum one invalid partition per test case (for single-fault assumption)

---

## Types of Defects 
* Defects in the handling of various data values
* Incorrect handling of valid input values
* Missing validation for invalid inputs
* Incorrect error messages or error handling
* Incorrect processing rules applied to a data group

---

See also:

* **[Test Matrix for an Input Field](./input-field-test-matrix.md)** - Practical applying EP to an Input Field.
* **[Equivalence Partitioning (EP) for Non‑Functional Requirements](./ep-templates-nbr.md)** - Practical templates for applying EP to NFRs.
* **[Boundary Value Analysis (BVA)](./bva.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Back to Main Page](./)**


