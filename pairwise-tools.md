[(Back to Main Page)](./)

# Pairwise Testing Tools

* **Pairwise testing** is a combinatorial method of software testing that, for each pair of input parameters to a system (typically software algorithms), tests all possible discrete combinations of those parameters.   

* **Minimum number of test cases:** For 2-wise is the product of the two largest parameters. Tools might generate more, but never less (for any n-wise coverage, the minimum baseline is always the product of the n largest parameters.)

* **The Assumption:* The results of a few tests are representative of all tests and that those few tests represent expected usage (e.g. in the area of medical devices under study by NIST, 66% of failures were triggered by a single variable and 97% by either one variable or two variables interaction).

* **The Domain Factor:** 2-wise testing is perfect for standard apps (e-commerce, web). However, highly complex or safety-critical domains (medical, FinTech) often require 3-wise or higher coverage to catch bugs hidden in complex logic.

## Online Tools
* **[Pairwise Teremok](https://pairwise.teremokgames.com/)** - A straightforward online combinatorial testing tool.
* **[Web version for PICT](https://pairwise.yuuniworks.com/)**  - An online interface for Microsoft's PICT tool, allowing you to generate cases without installation.

## Desktop & Console Tools
* **[Microsoft PICT](https://github.com/microsoft/pict)** - The industry-standard CLI tool from Microsoft. 📄 [Documentation & Instructions](https://github.com/microsoft/pict/blob/main/doc/pict.md) [My Forked Backup](https://github.com/olha-yatskivska/pict)
* **[ACTS (NIST/Rex Black)](https://csrc.nist.gov/projects/automated-combinatorial-testing-for-software/downloadable-tools)** - Advanced Combinatorial Testing System. A desktop tool that works with pairs, triplets, and n-wise combinations.
* **[AllPairs (James Bach)](https://www.satisfice.com/download/allpairs)** - Classic console tool using the "all pairs" algorithm. Includes Perl script and instructions.
* **[AllPairs for Mac](https://sourceforge.net/projects/allpairs/)** - A version of the classic AllPairs tool specifically compiled for macOS.


---

## Tool Comparisons

To see a collection of links related to pairwise tools and there comparisons conducted by a Microsoft employee (Jacek Czerwonka)

* [Original Repository](https://github.com/jaccz/pairwise) (Check here for the most up-to-date versions and updates)   

* [My Forked Backup](https://github.com/olha-yatskivska/pairwise) (Saved as a permanent backup in case the original is ever removed)

---

See also:

* **[Pairwise Testing Tools Comparison](https://docs.google.com/spreadsheets/d/1iwLri_iummO5VbK9NMeDdRIPQQAvaEdBTxWiUUDPObo/edit?usp=sharing)** - Practical Example Spreadsheets.
* **[Pairwise Testing](./pairwise.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Back to Main Page](./)**
  
