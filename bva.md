[(Back to Main Page)](./)

# Boundary Value Analysis (BVA)  

BVA is used to test the proper handling of values that exist on the boundaries of ordered equivalence partitions. It is an extension of Equivalence Partitioning and depends on correct partitioning as a prerequisite.

## Important considerations about boundary values:
* Identify all the equivalence partitions - the effectiveness of the boundary value tests depends on the correctness of the equivalence partitioning.
* Identify all the boundaries.
* Identify which partition each boundary belongs to.
* Since the boundary usually belongs to a particular partition, you can use it as a representative of this partition (but it's better not to skip non-boundary tests)
* If an input condition specifies a valid range between values x and y, then design test cases using:
   * The boundary values themselves: x, y
   * Values just outside the range: x − 1 step, y + 1 step
   * (For 3-value BVA) Values just inside the range: x + 1 step, y − 1 step
   * The step interval (e.g., 1, 0.1, 0.01) determines what "just below" and "just above" mean.
* Boundaries exist for both valid and invalid partitions. Both must be identified and tested for complete BVA coverage.

---

## Applicability   
* BVA is applicable at any test level and is appropriate when ordered equivalence partitions exist. For this reason the BVA technique is often conducted together with the EP technique. 
* In addition to number ranges, partitions for which boundary value analysis can be applied include: 
   * Numeric attributes of non-numeric variables (e.g. length)
   * The number of loop execution cycles, including loops in state transition diagrams
   * The number of iteration elements in stored data structures such as arrays
   * The size of physical objects, e.g. memory
   * The duration of activities

---

## Advantages
* Very good at exposing potential user interface/user input problems
* Very clear guidelines on determining test cases
* Very small set of test cases generated.

---

## Limitations/Difficulties
* Boolean (logical) variables present a problem for BVA
* BVA assumes the variables to be truly independent which is not always possible.
* Does not test dependencies between combinations of inputs.
* Pesticide paradox susceptibility — BVA produces deterministic, fixed test values (boundary ± step). Unlike EP, where testers can vary representative values across executions, BVA test cases use the exact same data every run, making this technique particularly vulnerable to the pesticide paradox.
* BVA applies only to ordered partitions.
* The accuracy depends on the accurate identification of the equivalence partitions in order to correctly identify the boundaries.
* The Test Analyst should also be aware of the precision in the valid and invalid values to be able to accurately determine the values to be tested. 

---

## Specification Keywords: Inclusive vs. Exclusive Boundaries
#### *✅ = boundary value is included in the range | ⬜  = boundary value is excluded*
* [x] up to - included
* [x] inclusively - included 
* [ ] less than, more than - not included (weight, height)
* [ ] below, above - not included
* [ ] before, after - not included (time, date)
* [ ] between - needs clarification

---

## Three-point BVA vs Two-point BVA

* Two-point BVA is the baseline technique: according to ISTQB, time-to-market, continuous delivery, optimal coverage
* Three-point BVA provides stronger defect detection and can detect off-by-one boundary displacement errors that 2-value BVA may miss: safety-critical domain, risky user story with high priority, the deepest coverage, for the higher risk items

| BVA Type | Lower Boundary Tests | Upper Boundary Tests | Total per Range |
| :-- | :-- | :-- | :-- |
| 2-value | LB − 1, LB | UB, UB + 1 | 4 |
| 3-value | LB − 1, LB, LB + 1 | UB − 1, UB, UB + 1 | 6 |

3-value BVA tests the boundary value and both its neighbors. This additional test point provides diagnostic precision to locate exactly where a displaced boundary moved, and detects subtle near-boundary defects in complex systems (rounding errors, caching issues, race conditions). The ISTQB syllabus states that 3-value BVA may detect off-by-one boundary displacement defects that 2-value BVA might miss.

---

## Boundary types / sources

| Type | Meaning | Example |
| :-- | :-- | :-- |
| Physical | Cannot exist | Percentage cannot be −5% or 105% |
| Logical | Does not fit within meaning | Human age cannot be 300 years |
| Voluntary | Business decision | Maximum discount capped at 30% |
| Technological | System constraint | 32-bit signed integer max: 2,147,483,647 |

---

## BVA Coverage

> **BVA Coverage (%) = (Number of boundary values tested ÷ Total number of identified boundary values) × 100**

---

## Defect Types Detected by BVA
* Finds displacement or omission of boundaries, or extra boundaries
* Defects regarding the handling of the boundary values, particularly errors with less-than and greater-than logic
* Non-functional defects (e.g. a system supports 10000 concurrent users but not 10001)

---

## EP/BVA Question Checklist

For each boundary between partitions, ask:

1. □ Is [boundary value] inclusive or exclusive for [partition]?
   → "Does exactly [value] belong to [A] or [B]?"

2. □ Is there a gap between [partition A] and [partition B]?
   → "If A ends at [X] and B starts at [Y], what about [values between]?"

3. □ Is there an overlap between [partition A] and [partition B]?
   → "[Value] satisfies both conditions. Which takes priority?"

4. □ Do all partitions together cover the entire input domain?
   → "Is every possible input handled by exactly one partition?"

---

See also:

* **[Test Matrix for an Input Field](./input-field-test-matrix.md)** - Practical applying EP to an Input Field.
* **[Equivalence Partitioning (EP)](./equivalence-partitioning.md)** - Practical templates for applying EP to NFRs.
* **[Boundary Value Analysis (BVA)](./bva.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Back to Main Page](./)**

