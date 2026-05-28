[Back to Main Page](./)

# Usability Evaluation

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)

> Note: These notes reference ISO 25010:2023 (Interaction Capability).
>  For exams based on older syllabi, ISO 25010:2011 (Usability) applies.

## Role of the Test Analyst
* Test Analysts are often in the position to coordinate and support the evaluation of usability.
* Test Analysts typically do not conduct usability testing themselves (that is the domain of usability specialists), but they design test conditions, define acceptance criteria from survey baselines (e.g., SUMI scores), and participate in or facilitate reviews.
* Usability defects may surface during functional testing but require distinct evaluation criteria.


## Usability Evaluation Strategies:
* Alpha testing — Internal users, controlled environment, early usability feedback
* Beta testing — Real users, production-like environment, broader usability and UX feedback before release

---

## Usability Aspects

| Aspect | Core Question | Focus |
| :-- | :-- | :-- |
| Usability | Can they use it? | Task completion (effectiveness, efficiency, satisfaction) |
| User Experience (UX) | Do they enjoy using it? | Emotional response, engagement, motivation, trust, frustration beyond engagement |
| Accessibility | Can everyone use it? | Inclusive design for diverse abilities and contexts |

--- 

## Usability
* Usability testing targets software defects that impact a user's ability to perform tasks via the user interface.
* Such defects may affect the user's ability to achieve their goals effectively, or efficiently, or with satisfaction.
* Usability problems can lead to confusion, error, delay, or outright failure to complete some task on the part of the user.

## The following are the sub-characteristics of usability [ISO 25010] for their definitions:

* **Appropriateness recognizability (understandability)** - Degree to which users can recognize whether a product or system is appropriate for their needs.

* **Learnability** - Degree to which the functions of a product or system can be learnt by specified users within a specified amount of time.

* **Operability** - Degree to which a product or system has attributes that make it easy to operate and control.

* **User error protection** - Degree to which a system prevents users against operation errors.

* **Self-descriptiveness** - Degree to which a product presents appropriate information, where needed by the user, to make its capabilities and use immediately obvious to the user without excessive interactions with a product or other resources (such as user documentation, help desks or other users). 

| Sub-Characteristic | Rationale |
| :-- | :-- |
| Appropriateness Recognizability | Can the user quickly identify if the product meets their needs? |
| Learnability | Can specified users learn the system within a specified time? |
| Operability | Is the system easy to operate and control? |
| User Error Protection | Does the system prevent operational errors? |
| Self-descriptiveness | Does the product make its capabilities immediately obvious without external help? |
---

## User Experience (UX)

From ISO 25010:
* **User engagement** - Degree to which a user interface presents functions and information in an inviting and motivating manner encouraging continued interaction.

| Sub-Characteristic | Rationale |
| :-- | :-- |
| User Engagement | Does the UI present information in an inviting and motivating manner encouraging continued interaction? |


> This is distinctly about how the user feels — satisfaction, pleasure, motivation — going beyond mere functional ease of use.

Typical factors which influence user experience include the following:

* Brand image (the user's trust in the manufacturer)

* Interactive behavior

* The helpfulness of the test object, including help system, support and training

## Accessibility (Inclusive Design for All Users)

From ISO 25010:
* **Inclusivity** - Degree to which a product or system can be used by people of various backgrounds (such as people of various ages, abilities, cultures, ethnicities, languages, genders, economic situations, etc.).
* **User assistance** - Degree to which a product can be used by people with the widest range of characteristics and capabilities to achieve specified goals in a specified context of use.

| Sub-Characteristic | Rationale |
| :-- | :-- |
| Inclusivity | Covers diverse backgrounds: age, culture, ethnicity, language, gender, economic situation, etc. |
| User Assistance | Covers the widest range of characteristics and capabilities to achieve goals in a specified context (physical, cognitive, sensory — including assistive technology users) |


### Accessibility testing should consider the relevant standards, and legislation: 
* the Web Content Accessibility Guidelines (WCAG);
* Equality Act 2010 (England, Scotland, Wales);
* Disability Discrimination Acts (Northern Ireland, Australia);
* Section 508 (US).

  ---

  ## Usability Evaluation Approach
  > ISO 9241-11:2018 Ergonomics of human-system interaction
  > Part 11: Usability: Definitions and concepts.
  > Usability is always measured within a specified context of use (users, tasks, equipment, environment).
  
  * **Usability testing:** is directed at measuring the following:
     * Effectiveness -  Do I achieve what I want and application helps me?
     * Efficiency -  How many resources (time, mental, etc.) I need to achieve what I want?
     * Satisfaction
  
   > Usability testing in a usability lab typically employs the think-aloud protocol (users verbalise thoughts while performing tasks).
   > Usability testing often leverages user personas and usage scenarios to guide test design
  
  * **Usability reviews**:
     * Inspections and reviews are a type of testing conducted from a usability perspective which help to increase the user's level of involvement. 
     * Heuristic evaluation (systematic inspection of a user interface design for usability) can be used to find the usability problems in the design so that they can be addressed as part of an iterative design process. Heuristic evaluation involves experts reviewing the interface against established usability principles to identify issues - [Nielsen's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/).

  
  * **Usability surveys and questionnaires**
    * Survey and questionnaire techniques may be applied to gather observations and feedback regarding user behavior with the system.
    * Standardized and publicly available surveys such as:
       *  [SUMI (Software Usability Measurement Inventory)](https://sumi.uxp.ie/index.html) - can provide a set of completion/acceptance criteria. SUMI produces quantitative psychometric data for comparative analysis.
       *  [WAMMI (Website Analysis and Measure Inventory)](https://www.wammi.com/report.html) -  focuses on website usability.

---
## Tie Evaluation Methods to What They Measure

| Method | What it Yields | Who Performs It |
| :-- | :-- | :-- |
| Usability Testing (lab) | Effectiveness, Efficiency, Satisfaction metrics | Representative users |
| Heuristic Evaluation | Usability defect identification against principles | Usability experts |
| Surveys (SUMI / WAMMI) | Subjective user perception data | End users |
  
---

## Usage in Test Analysis:
* [Checklist: Usability Heuristics for Review](./review-usability-checklist.md) 
* [Accessibility Test Analysis Checklist](./checklist-accessibility.md)
* [Usability Test Analysis Checklist](./checklist-usability.md)
