[Back to Main Page](./)

# Portability Testing

> Sources:
> * Certified Tester Advanced Level Test Analyst (CTAL-TA) Syllabus
> * Course ISTQB Advanced Test Analyst from the [Trainer Alexandra Kovalova](https://certifiedunicorns.pro/advancedistqb?utm_source=telegram&utm_medium=webinar-agile-anons&utm_campaign=25-05)

Portability tests relate to the degree to which a software component or system can be transferred into its intended environment, either as a new installation, or from an existing environment.

The ISO 25010 classification of product quality characteristics includes the following sub-characteristics of portability:
  * Installability
  * Adaptability (Cross-Browser testing)
  * Replaceability (Migration from one platform to another (from C# to Go lang))

The task of identifying risks and designing tests for portability characteristics is shared between the Test Analyst and the Technical Test Analyst.


## Installability Testing

* Installability testing is conducted on the software and written procedures are used to install and de-install the software on its target environment.

* The typical testing objectives that are the focus of the Test Analyst include:

  * Validating that different configurations of the software can be successfully installed. Where a large number of parameters may be configured, the Test Analyst may design tests using the pairwise technique to reduce the number of parameter combinations tested and focus on particular configurations of interest (e.g., those frequently used).

  * Testing the functional correctness of installation and de-installation procedures.

  * Performing functional suitability tests following an installation or de-installation to detect any defects which may have been introduced (e.g., incorrect configurations, functions not available).
  
  * Identifying usability issues in installation and de-installation procedures (e.g., to validate that users are provided with understandable instructions and feedback/error messages when executing the procedure).

  * Testing updates, upgrades, and patches: a new service pack, a new version biuilds, updated libraries, NuGet Packages.

---
 
## Adaptability Testing 

* Adaptability testing checks whether a given application can be adapted effectively and efficiently to function correctly in all intended target environments (hardware, software, middleware, operating system, cloud, etc.).

* The Test Analyst supports adaptability testing by identifying the intended target environments (e.g., versions of different mobile operating systems supported, different versions of browsers which may be used), and designing tests that cover combinations of these environments.

* The target environments are then tested using a selection of functional suitability test cases which exercise the various components present in the environment.

---

## Replaceability Testing

* Replaceability testing focuses on the ability of software components or versions within a system to be exchanged for others.

* This may be particularly relevant for system architectures based on the Internet of Things, where the exchange of different hardware devices and/or software installations is a common occurrence.

> *Example:* a hardware device used in a warehouse to register and control stock levels may be replaced by a more advanced hardware device (e.g., with a better scanner) or the installed software may be upgraded with a new version that enables stock replacement orders to be automatically issued to a supplier’s system.

* Replaceability tests may be performed by the Test Analyst in parallel with functional integration tests where more than one alternative component is available for integration into the complete system.
