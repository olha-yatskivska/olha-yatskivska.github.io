[Back to Main Page](./)

## Advanced Concept: Analytical Coverage

When designing tests, **exhaustive coverage** (testing every single possible combination) is often mathematically impossible due to combinatorial explosion. Furthermore, some input fields have near-infinite possibilities. 

To solve this, making analytical decisions to group classes into **logical partitions** using Equivalence Partitioning and Boundary Value Analysis is the best solution. 

## Analytical Example: Microsoft Word Font Menu

Consider the Font Menu in Microsoft Word a user can select any font size from 1 to 1638. Creating a class (leaf node) for every single size is impossible. Instead, grouping the inputs into logical, testable partitions: **Small (8), Typical (12), and Large (72)**.

Here is the resulting Classification Tree based on analytical grouping:

```mermaid
graph TD
    Root(["Font"])
    
    %% Classifications (Parameters)
    Font["Font"]
    Style["Style"]
    Strikethrough["Strikethrough"]
    Height["Height"]
    Caps["Caps"]

    Root --> Font
    Root --> Style
    Root --> Strikethrough
    Root --> Height
    Root --> Caps


    %% Define the style once
    classDef noBorder stroke-width:0px;

    %% Classes (Partitions) - Style applied directly using :::
    Font --> Small_8["Small(8)"]:::noBorder
    Font --> Typical["Typical(12)"]:::noBorder
    Font --> Large["Large(72)"]:::noBorder

    Style --> Regular["Regular"]:::noBorder
    Style --> Italic["Italic"]:::noBorder
    Style --> Bold["Bold"]:::noBorder
    Style --> Bold_ital["Bold ital"]:::noBorder
    

    Strikethrough --> No["No"]:::noBorder
    Strikethrough --> Yes["Yes"]:::noBorder
    Strikethrough --> Double["Double"]:::noBorder

    Height --> Normal["Normal"]:::noBorder
    Height --> Subscript["Subscript"]:::noBorder
    Height --> Superscript["Superscript"]:::noBorder

    Caps --> Normal_caps["Normal"]:::noBorder
    Caps --> Small_caps["Small caps"]:::noBorder
    Caps --> All["All caps"]:::noBorder
```

## Why this approach matters:
By applying analytical grouping, we reduce the "Font Size" parameter from 1,638 possible inputs down to just 3 highly effective test classes. When combined with Pairwise (2-wise) testing across the other classifications (Style, Strikethrough, Height, Caps), we can achieve maximum defect detection with a minimal, highly efficient number of test cases.
   
  
--- 

See also:

* **[Classification Tree Examples](./classification-tree-examples)** - Practical Example.
* **[Classification Tree Testing](./classification-tree.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Classification Tree Tools](./classification-tree-tools.md)** - Links for the most popular tools.
* **[Back to Main Page](./)**

