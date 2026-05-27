[Back to Main Page](./)

# Use Case Testing

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)


A Use Case is a specification-based artifact that describes interactions between actors (humans, external systems, or hardware) and the system under test to achieve a specific goal. Each use case defines a contract of behavior from the user's perspective.
Each Use Case should describe a single, well-defined scenario. 
  

---

* Use case testing provides transactional, scenario-based tests that should emulate intended use of the component or system specified by the use case. Use cases are defined in terms of interactions between the actors and a component or system that accomplishes some goal. 

* Actors can be human users, external hardware, or other components or systems.

---
## Classification

* Type: Specification-based (Black-box) test technique
* Level: System testing, Acceptance testing (primarily); Integration testing (occasionally)
* Basis: Use case specifications, user stories with acceptance criteria

---

## Use case structure ([See example](https://drive.google.com/file/d/16oliLF85i-kHR-oBaY9kCy7bEPyyyq5J/view?usp=sharing))

* Main path/basic scenario or happy path 
* Alternate paths
* Exception paths or error handling

Note: The tester can go from different steps from the main path to another Use Case. 

## The mechanic of Use Case technique
* One test case on main path (better if there will be no more then 10 steps)
* One test case per alternative path - can be a part of main path or combine if have limited time
* Mandatory one test case on each exception path - to prevent masking of defects.
* The Tester for each of steps can apply test techniques (BVA, EP, Decision Table, etc.) if it applicable
* [See practical example](./use-case-test-cases.md)

## ATN scenarios example

Use cases for ATM could describe the following scenarios:
* Rejecting an invalid ATM card
* Logging into the system by entering the correct PIN
* Correctly withdrawing money from an ATM
* Attempted failed withdrawal of money due to insufficient funds in the account
* Locking the card by entering the wrong PIN three times

For each use case, the tester can construct a corresponding test case, as well as a set of test cases to check the occurrence of unexpected events during the scenario run. 

---

## Sources of use cases and user flows

* User Experience department (UX) 
* Product Managers (product metrics)
* Marketing Team
* Analyst
* Statistics of user behavior on the website/mobile app (Google Analytics)
* SEO specialist

---

## Applicability

* Use case testing is usually applied in system and acceptance testing. It may also be used in integration testing if the behavior of the components or systems is specified by use cases. 

* Use cases are also often the basis for performance testing because they portray realistic usage of the system.

* The scenarios described in the use cases may be assigned to virtual users to create a realistic load on the system (so long as load and performance requirements are specified in them or for them).


---

## Limitations/Difficulties

* In order to be valid, the use cases must convey realistic user transactions.

* Use case specifications are a form of system design. The requirements of what users need to accomplish should come from users or user representatives, and should be checked against organizational requirements before designing corresponding use cases.

* The value of a use case is reduced if it does not reflect real user and organizational requirements, or hinders rather than assists completion of user tasks.

* An accurate definition of the exception, alternative and error handling behaviors is important for the coverage to be thorough.

* Use cases should be taken as a guideline, but not a complete definition of what should be tested as they may not provide a clear definition of the entire set of requirements.

* It may also be beneficial to create other models, such as flowcharts and/or decision tables, from the use case narrative to improve the accuracy of the testing and to verify the use case itself.

* As with other forms of specification this is likely to reveal logical anomalies in the use case specification, if they exist.

---

## Coverage

* The minimum acceptable level of coverage of a use case is to have one test case for the basic behavior and sufficient additional test cases to cover each alternative and error handling behavior.

* If a minimal test suite is required, multiple alternative behaviors may be incorporated into a test case provided they are mutually compatible.

* If better diagnostic capability is required (e.g., to assist in isolating defects), one additional test case per alternative behavior may be designed, although nested alternative behaviors will still require some of those behaviors to be amalgamated into a single test case (e.g., termination versus non-termination alternative behaviors within a "retry" exception behavior).

* Coverage is measured as: (number of use case behaviors exercised / total number of use case behaviors) × 100%
Where "behaviors" = main path + all alternative paths + all exception paths.

---

## Types of Defects

Defects include: 
* Mishandling of defined behaviors
* Missed alternative behaviors
* Incorrect processing of the conditions presented
* Poorly implemented or incorrect error messages. 

---

## Relationship to other techniques
* Use cases define WHAT to test (scenarios); within each step, apply:
  - EP/BVA for input fields
  - Decision tables for complex business rules at decision points
  - State transition testing if the use case implies state changes
* Use cases are complemented by:
  - Exploratory testing (for behaviors NOT described in use cases)
  - Error guessing (for exceptions not yet documented)

---

See also:

* **[Use Case Test Cases](./use-case-test-cases.md)** -  Practical Example of designing test cases.
* **[Back to Main Page](./)**

