[Back to Main Page](./)

**Use case:** [Use case Example](https://drive.google.com/file/d/16oliLF85i-kHR-oBaY9kCy7bEPyyyq5J/view?usp=sharing)   

**Coverage:** Minimum suite = one test case per path (main + each alternative + each exception) and suggestions for additional test cases, clarifing questionts to BA 
                                                         

## Main scenario

TC-V-01: Main Scenario - Successful Course Registration
Objective: Verify that an ITP with a valid voucher can complete full registration flow end-to-end.

Precondition: ITP has a valid voucher code; SP is accessible; course has available spots (<12 participants registered)
| # | Test step | Expected result|
| :--- | :--- | :--- |
| 1 | Launch SP  | SP's home page is shown and requests a voucher code from the ITP. |
| 2 | Enter the voucher code (valid EP + BVA) | SP lists the dates, locations and current number of registreted participants for the course indicated in the voucher code. |
| 3 | Select a date and location  | SP shows an overview of the selected course's contents. |
| 4 | Confirm selection of this course by pressing the "Register" button  | SP places the ITP onto the list of participants and a message shown "You are registered for the course". SP updates the participants list. |
| 5 | Log out | SP's login page is shown |

Postcondition: ITP appears on participants list; participant count incremented by 1; voucher is consumed (clarify with BA: can it be reused?)

---

## Alternative flow steps:

TC-V-02 Alternative flow from 2a - Logout from Home Page

Preconditions: ITP has access to SP; SP is accessible

| # | Test step | Expected result|
| :--- | :--- | :--- |
| 1 | Launch SP  | SP's home page is shown and requests a voucher code from the ITP. |
| 2 | Log out from the application's home page  | SP's login page is shown |

Postcondition: No registration occurs; system state unchanged; session terminated

Additional test cases:
1. Re-login after log out immediately
2. Re-login after log out after some time before the session timeout threshold
3. Log out from any step 2-4 from TC-V-01 Main Scenario with re-login immediately
4. Log out from any step 2-4 from TC-V-01 Main Scenario with re-login some time before the session timeout threshold
5. Session timeout: remain idle on any page (steps 1–4) beyond the session timeout threshold - verify SP handles expiry gracefully (redirect to login, no data corruption).
6. Log in to SP and change the PC user

TC-V-03 Alternative flow from 8a - Full Course, Waiting List

Precondition: ITP has a valid voucher code; SP is accessible; the selected course already has exactly 12 participants registered

| # | Test step | Expected result|
| :--- | :--- | :--- |
| 1 | Repeat steps 1-3 from main scenario test case |  Same expected results as main scenario steps 1-3 |
| 2 | Confirm selection of this course by pressing the "Register" button |  SP places the ITP onto a waiting list and a message shown "You are on the waiting list". SP updates the waiting list. |
| 3 | Log out | SP's login page is shown |

Postconditions: ITP appears on the waiting list (not on participants list); participant count remains 12; waiting list count incremented by 1

Additional test cases:

BVA for participant limit boundary:
1. 11 participants → registration succeeds (below limit)
2. 12 participants → registration succeeds (at limit, last spot)
3. Simultaneously two 12th participants  → registration succeeds for one (at limit, last spot), another into waiting list   
4. 13th participant → placed on waiting list (above limit)

Carify with BA:  
1. Change the date: If ITP is on waiting list for Date A, can he switch to date B where spots are available?
2. Change the location: If location A is full, can ITP select Location B that isn't full 
3. Change the date and the location the same questions
4. If ITP can change how he can do it? go back and select a different date/loction? Canceling his waiting list position before or after? Cn be on multiple waiting lists?
5. What is the limit for waiting list?
   
---

## Exceptions

TC-inV-01 Exception E1 -  Invalid Voucher Code

Precondition: ITP has access to SP; SP is accessible; ITP has an invalid voucher code AND a valid voucher code (for recovery verification)

| # | Test step | Expected result|
| :--- | :--- | :--- |
| 1 | Launch SP  | SP's home page is shown and requests are voucher code from the ITP. |
| 2 | Enter invalid voucher code (invalid EP + BVA) | SP shows a message "Voucher not known - please try again". SP returns to the home page |
| 3 | Verify home page is functional (can enter new valid voucher code) | SP accepts valid voucher code |
| 4 | Log out | SP's login page is shown |

Postcondition: No registration occurs after invalid attempt; system remains functional; home page is accessible for retry

Clarify with BA + Security team
1. Is there a max number of invalid attempts per session?
2. Is there a lockout mechanism after N failures?
3. Is there a time delay between attempts?
4. is the account locked or just the session?

*Note: If we won't implement it (the financial damage from brute-forced voucher is minimal) - write down it into the one-page test plan or risk-analyze documentation about accepting the risk.* 

TC-inV-02 Exception E2 - No Courses Available

Precondition: ITP has a valid voucher code; SP is accessible; no courses are available for the voucher code's indicated course

| # | Test step | Expected result|
| :--- | :--- | :--- |
| 1 | Launch SP  | SP's home page is shown and requests are voucher code from the ITP. |
| 2 | Enter the voucher code | SP shows a message "Sorry no courses available - please log out and talk to your manager". Returns to the home page
| 3 | Log out | SP's login page is shown |

Postcondition: No registration occurs; system returns to home page; ITP can log out cleanly


Clarify with BA
1. What if ITP is already registered for the same course?

---

TC-E2E-01 Error Recovery into Capacity Boundary Path

Precondition: ITP has a valid voucher code; SP is accessible; course has no available spots (12 participants)

| # | Test step | Expected result|
| :--- | :--- | :--- |
| 1 | Launch SP  | SP's home page is shown and requests a voucher code from the ITP. |
| 2 | Enter invalid voucher code (invalid EP + BVA) | SP shows a message "Voucher not known - please try again". SP returns to the home page |
| 3 | Verify home page is shown and functional | Home page is displayed; voucher input field is accessible and empty |
| 4 | Enter the valid voucher code (valid EP + BVA) | SP lists the dates, locations and current number of registered participants for the course indicated in the voucher code. |
| 5 | Select a date and location  | SP shows an overview of the selected course's contents. |
| 6 | Confirm selection of this course by pressing the "Register" button  | SP places the ITP onto a waiting list and a message shown "You are on the waiting list". SP updates the waiting list. |
| 7 | Log out | SP's login page is shown |

Postcondition: ITP appears on the waiting list; participant count remains 12; waiting list count is incremented by 1 


---

## Traceability Matrix

| Test Case | Covers UC Steps | Covers Paths | Classification | Purpose |
| :-- | :-- | :-- | :-- | :-- |
| TC-V-01 | 1–9 | Main | Minimum suite | Verifies happy path in isolation |
| TC-V-02 | 1–2, 2a | Alternative | Minimum suite | Verifies early exit path |
| TC-V-03 | 1–8a, 9 | Alternative | Minimum suite | Verifies capacity boundary in isolation |
| TC-inV-01 | 1–3 (E1) | Exception | Minimum suite | Verifies error handling in isolation |
| TC-inV-02 | 1–4 (E2) | Exception | Minimum suite | Verifies unavailability handling in isolation |
| TC-E2E-01 | E1 → 3–8a, 9 | Exception + Alternative | Additional | Recovering after error handling - realistic test case: Entering wrong data and getting into waiting list |


See also:

* **[Use Case testing](./use-case-testing.md)** -  Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Back to Main Page](./)**
