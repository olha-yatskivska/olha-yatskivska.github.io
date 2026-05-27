# Test Matrix for an Input Field

> Source: C. Kaner, J.Bach, B. Pattichord "Lessons Learned in Software Testing"

For convenience, the Test Matrix is provided in [Spreadsheets](https://docs.google.com/spreadsheets/d/1iwLri_iummO5VbK9NMeDdRIPQQAvaEdBTxWiUUDPObo/edit?gid=571842728#gid=571842728)

## A catalog of additional tests

* [ ] Enter nothing but wait for a long time before pressing the Enter or Tab key, clicking OK, or doing something equivalent that takes you out of the field. Is there a time-out? What is the effect?

* [ ] Enter one digit but wait for a long time before entering another digit or digits and then press the Enter key. How long do you have to wait before the system times you out, if it does? What happens to the data you entered? What happens to other data you previously entered?

* [ ] Enter digits and edit them using the backspace key, and delete them, and use arrow keys (or the mouse) to move you into the digits you’ve already entered so that you can insert or overtype new digits.

* [ ] Enter digits while the system is reacting to interrupts of different kinds (such as printer activity, clock events, mouse movement and clicks, files going to disk, and so on).

* [ ] Enter a digit, shift focus to another application, return to this application. Where is the focus?
