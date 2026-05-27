[(Back to Main Page)](./)

# Test Matrix for an Input Field

> Source: C. Kaner, J.Bach, B. Pattichord "Lessons Learned in Software Testing"

For convenience, the Test Matrix is provided in [Spreadsheets](https://docs.google.com/spreadsheets/d/1aibTRwH8TQT3JxSCYpMs6LWy-EzLxQo5QEkTkILl1jA/edit?usp=sharing)

## A catalog of additional tests

* [ ] Enter nothing but wait for a long time before pressing the Enter or Tab key, clicking OK, or doing something equivalent that takes you out of the field. Is there a time-out? What is the effect?

* [ ] Enter one digit but wait for a long time before entering another digit or digits and then press the Enter key. How long do you have to wait before the system times you out, if it does? What happens to the data you entered? What happens to other data you previously entered?

* [ ] Enter digits and edit them using the backspace key, and delete them, and use arrow keys (or the mouse) to move you into the digits you’ve already entered so that you can insert or overtype new digits.

* [ ] Enter digits while the system is reacting to interrupts of different kinds (such as printer activity, clock events, mouse movement and clicks, files going to disk, and so on).

* [ ] Enter a digit, shift focus to another application, return to this application. Where is the focus?

---

## Input Testing - Hidden Traps

### Invisible Characters (paste-specific)

| Unicode | Name | Source |
|:--|:--|:--|
| U+200B | Zero-Width Space | CMS, websites |
| U+200C | Zero-Width Non-Joiner | Multilingual text |
| U+200D | Zero-Width Joiner | Emoji, copy-paste |
| U+FEFF | BOM | Files, APIs |
| U+00A0 | Non-Breaking Space | Web pages, Word |
| U+00AD | Soft Hyphen | Word processors |

> Keyboard cannot produce these. Always test paste separately.


### ASCII Boundaries for Numeric Fields

| Boundary | Char | ASCII | Use When |
|:--|:--|:--|:--|
| Just below 0 | `/` | 47 | Numeric-only fields |
| Just above 9 | `:` | 58 | Numeric-only fields |
| Just below A | `@` | 64 | Alpha-only fields |
| Just above Z | `[` | 91 | Alpha-only fields |
| Just below a | `` ` `` | 96 | Alpha-only fields |
| Just above z | `{` | 123 | Alpha-only fields |

 
### Unicode Traps (if in Expression is using [0-9] instead of \d)

| Input | Risk |
|:--|:--|
| `١٢٣٤٥` (Arabic digits) | Python \d matches these |
| `𝟏𝟐𝟑𝟒𝟓` (Math bold) | Looks identical to 12345 |
| `１２３４５` (Fullwidth) | Common in Japanese input |

---

See also:

* **[Equivalence Partitioning (EP)](./equivalence-partitioning.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Equivalence Partitioning (EP) for Non‑Functional Requirements](./ep-templates-nbr.md)** - Practical templates for applying EP to NFRs.
* **[Back to Main Page](./main?search=1#readme)**


