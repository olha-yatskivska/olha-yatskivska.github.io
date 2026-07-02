[Back to Main Page](./)

# Checklist-Based Testing

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)

* When applying the checklist-based test technique, an experienced Test Analyst uses a high-level, generalized list of items to be noted, checked, or remembered, or a set of rules or criteria against which a test object has to be verified. 

* These checklists are built based on a set of standards, experience, and other considerations.

* In Agile software development, checklists can be built from the acceptance criteria for a user story.

> Example: a user interface standard checklist can be employed as the basis for testing an application. 

---

## Applicability

* Checklist-based testing is most effective in projects with an experienced test team that is familiar with the software under test or familiar with the area covered by the checklist (e.g., to successfully apply a user interface checklist, the Test Analyst may be familiar with user interface testing but not the specific system under test).  Because checklists are high-level and tend to lack the detailed steps commonly found in test cases and test procedures, the knowledge of the tester is used to fill in the gaps. By removing the detailed steps, checklists are low maintenance and can be applied to multiple similar releases.

* Checklists are well-suited to projects where software is released and changed quickly. This helps to reduce both the preparation and maintenance time for test documentation.

* They can be used for any test level and are also used for regression testing and smoke testing.

--- 

## Limitations/Difficulties

* The high-level nature of the checklists can affect the reproducibility of test results. It is possible that *several testers will interpret the checklists differently* and will follow different approaches to fulfil the checklist items. This may cause *different test results*, even though the same checklist is used. This can result in *wider coverage* but *reproducibility is sometimes sacrificed*.

* Checklists may also result in over confidence regarding the level of coverage that is achieved since the actual testing depends on the tester’s judgment.

* Checklists can be derived from more detailed test cases or lists and tend to grow over time. Maintenance is required to ensure that the checklists are covering the important aspects of the software under test.

---

## Coverage

* Coverage can be determined by taking the number of checklist items tested divided by the total number of checklist items and stating coverage as a percentage.

* The coverage is as good as the checklist but, because of the high-level nature of the checklist, the results will vary based on the Test Analyst who executes the checklist.

---

## Types of Defects

* Typical defects found with this technique cause failures resulting from varying the data, the sequence of steps or the general workflow during testing.

---

## Sources for Checklist-Based Testing

To avoid duplication, checklists are mapped directly to their relevant Quality Characteristics within this toolbox:

* **[Usability/Accesability](./interaction-capability-usability.md)** - Includes UI/UX heuristics and WCAG accessibility checklists. 

* **[Security](.security.md)** - Includes OWASP standards and API security checklists.

* **Platform Compliance:** Mandatory checklists for mobile release:
  * [App Store Guidlines](https://developer.apple.com/app-store/review/guidelines/)
  * [Google Play’s Developer Program Policies and guidelines](https://transparency.google/intl/en/our-policies/product-terms/google-play/)

* **Industry Specifications & Standards:** Domain-specific business rules, legal requirements (e.g., GDPR, HIPAA), and RFC documents.
