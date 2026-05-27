[Back to Main Page](./)

# Complex Dependencies (Nested Classifications)

## The Concept
In the Classification Tree Method, **Hierarchical Dependencies** occur when a parameter (classification) is only relevant based on the selection of a previous class. Instead of creating complex constraints to block invalid combinations, we nest the dependent parameter directly under the relevant class. 

## Scenario: Graphic Object Generator
Imagine we are testing a simple graphic design tool that generates shapes based on user input.

### Requirements:
* **R-01.** Every generated entity must have a defined **Colour** and **Shape**.
* **R-02.** Available colours are Red, Blue, and Green.
* **R-03.** Available shapes are Triangle and Circle.
* **R-04.** If a **Triangle** is selected, the system requires the user to specify a **Size** (Small or Large).
* **R-05.** If a **Circle** is selected, the size is fixed by the system, and the Size parameter is disabled/hidden from the user.

Based on these rules, we nest the "Size" classification directly under the "Triangle" class:

```mermaid
graph TD
    Root(["Entity"])
    
    %% Classifications (Parameters)
    Colour["Colour"]
    Shape["Shape"]
     
    Root --> Colour
    Root --> Shape
 
    %% Define the style once
    classDef noBorder stroke-width:0px;

    %% Classes (Partitions) - Style applied directly using :::
    Colour --> Red["Red"]:::noBorder
    Colour --> Blue["Blue"]:::noBorder
    Colour --> Green["Green"]:::noBorder

    Shape --> Triangle["Triangle"]:::noBorder
    Shape --> Circle["Circle"]:::noBorder

   
    Triangle --> Size["Size of triagle"]

    
 
    Size --> Small["Small"]:::noBorder
    Size --> Large["Large"]:::noBorder

```

## Combination Table (Handling Dependencies)

When creating the test cases, notice how the Size columns are handled. If "Circle" is selected, the Size classes are marked with a dash (-) because they are logically impossible and out of scope for that test case.

*(Note: This table demonstrates Minimal Coverage, ensuring every valid leaf node is hit at least once)*

| Test Case | Red | Blue | Green | Triangle | Circle | Small | Large |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| TC1 | ● |  |  | ● |  | ● |  |
| TC2 |  | ● |  | ● |  |  | ● |
| TC3 |  |  | ● |  | ● | - | - |

## 💡 Why this is effective:
If we had put "Size" at the top level next to "Colour" and "Shape", we would have generated test cases like (Green, Circle, Small). We would then have to write extra constraints to invalidate them. By nesting the dependency visually in the tree, we prevent invalid combinations from ever being generated in the first place!


See also:

* **[Classification Tree Examples](./classification-tree-examples)** - Practical Example.
* **[Classification Tree Testing](./classification-tree.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Classification Tree Tools](./classification-tree-tools.md)** - Links for the most popular tools.
* **[Back to Main Page](./)**
