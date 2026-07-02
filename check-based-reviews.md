[Back to Main Page](./)


# Checklist-based reviewing

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)


Checklist-based reviewing is the most common technique used by a Test Analyst when reviewing the test basis. 
Checklists are used during reviews to remind the participants to check specific points during the review. 
They can also help to de-personalize the review (e.g., " This is the same checklist we use for every review. We are not targeting only your work product.").

Checklist-based reviewing can be performed generically for all reviews or can focus on specific quality characteristics, areas or types of documents. For example, a generic checklist might verify the general document properties such as having a unique identifier, no references marked “to be determined”, proper formatting and similar conformance items. 
A specific checklist for a requirements document might contain checks for the proper use of the terms “shall” and “should”, checks for the testability of each stated requirement, and so forth.

The format of the requirements may also indicate the type of checklist to be used. 
A requirements document that is in narrative text format will have different review criteria than one that is based on diagrams.

Checklists may also be oriented toward a particular aspect, such as:
* A programmer/architect skill set or a tester skill set - in the case of the Test Analyst, the tester skill set checklist would be the most appropriate
* A certain risk level (e.g., in safety-critical systems) - the checklists will typically include the specific information needed for the risk level
* A specific test technique - the checklist will focus on the information needed for a particular technique (e.g., rules to be represented in a decision table)
* A particular specification item, such as a requirement, use case or user story - these are discussed in the following sections and generally have a different focus than those used by a Technical Test Analyst for the review of code or architecture


## Requirements Reviews

The following items are an example of what a requirements-oriented checklist could include:
* Source of the requirement (e.g., person, department)
* Testability of each requirement
* Priority of each requirement
* Acceptance criteria for each requirement
* Availability of a use case calling structure, if applicable
* Uniqueidentification of each requirement/use case/user story
* Versioning of each requirement/use case/user story
* Traceability for each requirement from business/marketing requirements
* Traceability between requirements and/or use cases (if applicable)
* Use of consistent terminology (e.g., uses a glossary)

It is important to remember that if a requirement is not testable, meaning that it is defined in such a way that the Test Analyst cannot determine how to test it, then there is a defect in that requirement.

> *Example:* a requirement that states “The software should be very user friendly” is untestable. How can the Test Analyst determine if the software is user friendly, or even very user-friendly? If, instead, the requirement says “The software must conform to the usability standards stated in the usability standards document, version xxx”, and if the usability standards document exists, then this is a testable requirement. It is also an overarching requirement because this one requirement applies to every item in the interface. In this case, this one requirement could easily spawn many individual test cases in a non-trivial application. Traceability from this requirement, or perhaps from the usability standards document, to the test cases, is also critical because if the referenced usability specification should change, all the test cases will need to be reviewed and updated as needed.

A requirement is also untestable if the tester is unable to determine whether the test passed or failed, or is unable to construct a test that can pass or fail. 

> *Example:* "System shall be available 100% of the time, 24 hours per day, 7 days per week, 365 (or 366) days a year" is untestable.


A simple checklist1 for use case reviews may include the following questions:

* [ ] Is the main behavior (path) clearly defined?
* [ ] Are all alternative behaviors (paths) identified, complete with error handling?
* [ ] Are the user interface messages defined?
* [ ] Is there only one main behavior (there should be, otherwise there are multiple use cases)?
* [ ] Is each behavior testable?

---

## User Story Reviews
In Agile software development, requirements usually take the form of user stories. These stories represent small units of demonstrable functionality. Whereas a use case is a user transaction that traverses multiple areas of functionality, a user story is a more isolated feature and is generally scoped by the time it takes to develop it. 

A checklist for a user story could include the following:

* [ ] Is the story appropriate for the target iteration/sprint?
* [ ] Is the story written from the view of the person who is requesting it?
* [ ] Are the acceptance criteria defined and testable?
* [ ] Is the feature clearly defined and distinct?
* [ ] Is the story independent of any others?
* [ ] Is the story prioritized?
* [ ] Does the story follow the commonly used format:
> As a <type of user >, I want < some goal > so that < some reason > 

If the story defines a new interface, then using a generic story checklist (such as the one above) and a detailed user interface checklist would be appropriate.

---

## Tailoring Checklists

A checklist can be tailored based on the following:

* [ ] Organization (e.g., considering company policies, standards, conventions, legal constraints)
* [ ] Project/development effort (e.g., focus, technical standards, risks)
* [ ] The type of work product being reviewed (e.g., code reviews might be tailored to specific programming languages)
* [ ] The risk level of the work product being reviewed
* [ ] Test techniques to be used

Good checklists will find problems and will also help to start discussions regarding other items that might not have been specifically referenced in the checklist. Using a combination of checklists is a strong way.
Using checklist-based reviewing with standard checklists such as those referenced in the Foundation Level syllabus and developing organizationally specific checklists such as the ones shown above will help the Test Analyst be
effective in reviews.

For more information on reviews and inspections see [Gilb93] and [Wiegers03]. 
