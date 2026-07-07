[Back to Main Page](./)

# Exploratory testing

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)


* Exploratory testing is characterized by the tester **simultaneously** learning about the test object and its defects, planning the testing work to be done, designing and executing the tests, and reporting the results. 

* The tester **dynamically** adjusts test goals during execution and prepares only lightweight documentation. 

---

## Applicability

* Good exploratory testing is planned, interactive, and creative.

* It requires little documentation about the system to be tested and is often used in situations where the documentation is not available or is not adequate for other test techniques.

* Exploratory testing is often used to add to other test techniques and to serve as a basis for the development of additional test cases.

* Exploratory testing is frequently used in Agile software development to get user story testing done flexibly and quickly with only minimal documentation.

* However, the technique may also be applied to projects using a sequential development model.

---

## Exploratory instruments

* Charters
* Heuristics
  * [Heuristic Test Strategy Model (HTSM)](https://github.com/olha-yatskivska/qa-artifacts/blob/main/test-planning/test-strategy/htsm.pdf) (Authored by [James Bach](https://www.satisfice.com/download/heuristic-test-strategy-model))
  * [Nielsen's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/)
* [Mnemonics](https://www.qualityperspectives.ca/resources/#mnemonics)
* Oracles

> Read more about chartes, session-based test management and more links about Exploratory Testing in [the blog "That's the buffet table"](https://thatsthebuffettable.blogspot.com/2017/07/pathway-exploratory-testing.html)

---

## Limitations/Difficulties

* Coverage of exploratory testing can be sporadic and reproducibility these tests performed can be difficult.
  
* Using test charters to designate the areas to be covered in a test session and time-boxing to determine the time allowed for the testing are techniques used to manage exploratory testing.
  
* At the end of a test session or set of test sessions, the Test Manager may hold a debriefing session to gather the test results and determine the test charters for the next test sessions.
  
* Another difficulty with exploratory testing sessions is to accurately track them in a test management system. This is sometimes done by creating test cases that are actually exploratory testing sessions.
  
* This allows the time allocated for the exploratory testing and the planned coverage to be tracked with the other test efforts.
  
* Since reproducibility may be difficult to achieve with exploratory testing, this can also cause problems when needing to recall the steps to reproduce a failure.
  
* Some organizations use the capture/playback capability of a test automation tool to record the steps taken by an exploratory tester.
  
* This provides a complete record of all activities during the exploratory testing session (or any experience-based testing session).
  
* Analyzing the details to find the actual cause of a failure can be tedious, but at least there is a record of all the steps that were involved.
  
* Others tools may be used to capture exploratory testing sessions but these don't record the expected results because they don’t capture the GUI interaction.

* In this case the expected results must be noted down so that proper analysis of defects can be undertaken if needed.

* In general, it is recommended that notes also be taken while performing exploratory testing, to support reproducibility where required.

---

## Coverage

* Test charters may be designed for specific tasks, objectives, and deliverables.

* Exploratory testing sessions are then planned to achieve those criteria.

* The charter may also identify where to focus the test effort, what is in and out of scope of the test session, and what resources should be committed to complete the planned tests.
  
* A test session may be used to focus on particular defect types and other potentially problematic areas that can be addressed without the formality of scripted testing.

---

## Types of Defects

* Scenario-based issues that are missed during scripted functional suitability testing
 
* Issues that fall between functional boundaries, and workflow related issues
  
* Performance and security issues are also sometimes uncovered during exploratory testing

---

> Read more about Exploratory Testing 3.0 from James Bach [here](https://www.satisfice.com/blog/archives/1509) and more [heuristics](https://www.satisfice.com/blog/archives/category/heuristics)
