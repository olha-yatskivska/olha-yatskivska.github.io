[Back to Main Page](./)

# Error Guessing

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)

* When using the error guessing technique, a Test Analyst uses experience to guess the potential errors that might have been made when the code was being designed and developed. 

* When the expected errors have been identified, a Test Analyst then determines the best methods to use to uncover the resulting defects.

* In addition to being used as a test technique, error guessing is also useful during risk analysis to identify potential failure modes. 

> Example: if a Test Analyst expects the software will exhibit failures when an invalid password is entered, tests will be run to enter a variety of different values in the password field to verify if the error was indeed made and has resulted in a defect that can be seen as a failure when the tests are run.


## Applicability

* Error guessing is done primarily during integration and system testing, but can be used at any test level. 

* This technique is often used with other techniques and helps to broaden the scope of the existing test cases.

* Error guessing can also be used effectively when testing a new release of the software to test for common defects before starting more rigorous and scripted testing.

> Note: [Defect taxonomies](./defect-taxonomies.md) are frequently used to identify common defects so you can apply those insights to your specific domain.

---

## Limitations/Difficulties

* Coverage is difficult to assess and varies widely with the capability and experience of the Test Analyst.

* It is best used by an experienced tester who is familiar with the types of defects that are commonly introduced in the type of code being tested.

* It is commonly used, but is frequently not documented and so may be less reproducible than other forms of testing

* Test cases may be documented but in a way that only the author understands and can reproduce.

---

## Coverage

* When a defect taxonomy is used, coverage is determined by taking the number of taxonomy items tested divided by the total number of taxonomy items and stating coverage as a percentage. 

* Without a defect taxonomy, coverage is limited by the experience and knowledge of the tester and the time available. 

* The quantity of defects found from this technique will vary based on how well the tester can target problematic areas.

--- 

## Types of Defects

Typical defects are usually those defined in the particular defect taxonomy or “guessed” by the Test Analyst, that might not have been found in black-box testing
