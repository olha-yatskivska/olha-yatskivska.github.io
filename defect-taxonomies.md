# Defect taxonomies 

* **Boris Beizer's Taxonomy** - Categorizes defects by origin (requirements, structural, data, integration, etc.) with empirical distribution data showing where bugs concentrate. Source: "Software Testing Techniques"


* **[Bug Taxonomies from Cem Kaner](https://kaner.com/pdfs/BugTaxonomies.pdf)** - Guidline for generating better tests.

* **[Orthogonal Defect Classification (ODC, IBM)](https://chillarege.com/docs/ODC/)** - Classifies each defect along multiple independent axes (type, trigger, qualifier, impact, etc.). Used for process feedback: the distribution of defect attributes reveals weaknesses in development/testing process rather than just cataloguing individual bugs.

---

* **[OWASP (Open Worldwide Application Security Project)](https://owasp.org/www-project-top-ten/)** - The standard awareness document representing the most critical security risks to web applications.
 
* **[CWE (Common Weakness Enumeration)](https://cwe.mitre.org/index.html)** - A list of weaknesses that can become vulnerabilities. Can be used for Root Cause Mapping. Besides Security, it can be mapped to the following ISO 25010 Quality Characteristics: 

1. Reliability
*Sub-characteristics affected: Availability, Fault Tolerance, Maturity, Recoverability*

| CWE Examples | Impact |
| :-- | :-- |
| CWE-476: NULL Pointer Dereference | Crashes → Availability |
| CWE-401: Missing Release of Memory | Memory leak → eventual failure |
| CWE-835: Infinite Loop | System hang → Availability |
| CWE-674: Uncontrolled Recursion | Stack overflow → crash |
| CWE-252: Unchecked Return Value | Unpredictable behavior → Fault Tolerance |
| CWE-404: Improper Resource Shutdown | Resource exhaustion → Recoverability |
| CWE-369: Divide By Zero | Crash → Maturity |

---

2. Performance Efficiency
*Sub-characteristics affected: Time Behaviour, Resource Utilization, Capacity*

| CWE Examples | Impact |
| :-- | :-- |
| CWE-400: Uncontrolled Resource Consumption | Resource utilization |
| CWE-407: Inefficient Algorithmic Complexity | Time behaviour |
| CWE-770: Allocation Without Limits or Throttling | Capacity |
| CWE-1046: String Concatenation for Immutable Text | Time behaviour |
| CWE-1067: Excessive Sequential Searches | Time behaviour |
| CWE-405: Asymmetric Resource Consumption | Resource utilization |

---

3. Maintainability
*Sub-characteristics affected: Modularity, Analysability, Modifiability, Testability*

| CWE Examples | Impact |
| :-- | :-- |
| CWE-1120: Excessive Code Complexity | Analysability, Testability |
| CWE-1047: Circular Dependencies | Modularity |
| CWE-1074: Excessively Deep Inheritance | Modifiability |
| CWE-561: Dead Code | Analysability |
| CWE-1080: Excessive Lines of Code in File | Analysability |
| CWE-1064: Excessive Number of Parameters | Modifiability |
| CWE-710: Improper Adherence to Coding Standards | All sub-characteristics |
| CWE-478: Missing Default Case | Testability |

---

4. Functional Suitability
*Sub-characteristics affected: Functional Correctness*

| CWE Examples | Impact |
| :-- | :-- |
| CWE-682: Incorrect Calculation | Correctness |
| CWE-193: Off-by-one Error | Correctness |
| CWE-681: Incorrect Numeric Type Conversion | Correctness |
| CWE-704: Incorrect Type Conversion or Cast | Correctness |
| CWE-192: Integer Coercion Error | Correctness |

---

5. Portability 
Sub-characteristics affected: Adaptability

| CWE Examples | Impact |
| :-- | :-- |
| CWE-474: Function with Inconsistent Implementations | Adaptability |
| CWE-589: Call to Non-ubiquitous API | Installability |

---

These mapping became [OMG Automated Quality Characteristic Measures standards](https://www.omg.org/spec/ASCQM/1.0/PDF) and are used in [ISO 5055 (Automated Source Code Quality Measures).](https://www.iso.org/obp/ui/en/#iso:std:iso-iec:5055:ed-1:v1:en)












