# Normalization

* Goal: Reduce redundancies, anomalies
* Evaluating and correcting table structures to minimize data redundancies
* Reduces data anomalies
* Assigns attributes to tables based on determination 
* Normal forms
  * First normal form \(1NF\)
  * Second normal form\(2NF\)
  * Third normal form\(3NF\)
* Structural point of view of normal forms
  * Higher normal forms are better than lower normal forms 
* Properly designed 3NF structures meet the requirement of fourth normal form\(4NF\)
* Denormalization: Produces a lower normal form 
  * Results in increased performance and greater data redundancy

### Need for Normalization

* Used while designing a new database structure
  * Analyzed the relationship among the attributes within each entity
  * Determines if the structure can be improved
* Improves the existing data structure and creates an appropriate database design

E.g. [A table could be normalized](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/Normalization/pics/07.png)

![ \[A table could be normalized\]\(http://bytes.usc.edu/cs585/s20\_db0ds1ml2agi/lectures/Normalization/pics/07.png\)](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/Normalization/pics/07.png)

## Normalization process

* objective is to ensure that each table conforms to the concept of well-formed relations
  * Each table represents a single subject
  * No data item will be unnecessarily stored in more than one table
  * All nonprime attributes in a table are dependent on the primary key
  * Each table is void of insertion, update, and deletion anomalies
* The process:
  * Ensures that all tables are in at least 3NF
  * Higher forms are not likely to be encountered in business environment
  * Works one relation at a time
  * Starts by:
    * Identifying the dependencies of a relation
    * Progressively breaking the relation into new set of relations

Normalization how-to, in one sentence: **work on one relation \(table\) at a time: identify dependencies, then 'normalize' - progressively break it down into smaller relations \(tables\), based on the dependencies we identify in the original relation** so that "only the PK, the whole PK and nothing but the PK" acts as a determinant!

### Functional Dependence Concepts

| Concept | Definition |
| :--- | :--- |
| Functional dependence | The attribute B is fully functionally dependent on the attribute A if each value of A determines one and only one value of B |
| Functional dependence \(Generalized definition\) | Attribute A determines attribute B if all of the rows in the table that agree in value for attribute A also agree in value for attribute B. |
| \(\(Fully Functional dependence\)\) | If attribute B is functionally dependent on a composite key A but not on any Subset of that composite key, the attribute B is fully functionally dependent on A. |

### Types of Functional Dependencies

* Partial dependency: Functional dependence in which the determinant is only part of the primary key
  * Assumption- One candidate key
  * Straight forward 
  * Easy to identify
* Transitive dependency: An attribute functionally depends on another nonkey attribute

If \(A,B\) is a primary key, we have **partial** dependence if \(A,B\)-&gt;\(C,D\) and B-&gt;C \[C is only partially dependent on the PK, ie. we only need B to determine C\].

If X is a primary key, we have a **transitive** dependency if X-&gt;Y and Y-&gt;Z \[Z is transitively dependent on X, not directly so\].

### Conversion to First Normal From

* Repeating group: Group of multiple entries of same type can exist for any single key attribute occurrence 
  * Existence proves the presence of data redundancies 
* Enable reducing data redundancies
* Steps
  * Eliminate the repeating groups
  * Identify the primary key
  * Identify all dependencies

In other words, "fill in the blanks" so that there are no nulls. Now we have a relation \(table\), with a value in each cell.

Further, identify the PK! In our example, it is \(PROJ\_NUM,EMP\_NUM\).

* Dependency diagram : Depicts all dependencies found within given table structure
  * Helps to get an overview of all relationships among table's attributes
  * Makes it less likely that an important dependency will be overlooked
  * Indicate full dependencies on the top, and partial and transitive dependencies on the bottom. "Top good, bottom bad". Also, color the PK components in a different color \(and underline them\). Result:
    * ![](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/Normalization/pics/16.png)

Create a **dependency diagram**, showing relationships \(dependencies\) between the attributes - this will help us systematically normalize the table.

* 1NF describes tabular format in which:
  * All key attributes are defined 
  * There are no repeating groups in the table
  * All attributes are dependent on the primary key
* All relational tables satisfy 1NF requirements
* Some tables contain partial dependencies 
  * Subject to data redundancies and various anomalies

### 1NF-&gt;2NF:

* Steps:
  * Make new tables to eliminate partial dependencies
  * Reassign corresponding dependent attributes
* Table is in 2NF when it:
  * Is in 1NF
  * Includes no partial dependencies

We eliminate partial dependencies by creating separate tables of such dependencies, and removing the dependent attributes from the starter table.

![](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/Normalization/pics/18.png)

### 2NF-&gt;3NF: remove transitive dependencies

We promote the non-prime keys that masquerade as PKs, into actual PKs \(give them their own tables\).

Whether we eliminate partial dependencies \(to create 2NF\) or transitive ones \(to create 3NF\), we follow the same process: create a new relation for each 'problem' dependency!

* Steps 
  * Make new tables to eliminate transitive dependencies 
    * Determinant: Any attribute whose value determines other values within a row
  * Reassign corresponding dependent attributes
* Table is in 3NF when it:
  * Is in 2NF
  * Contains no transitive dependencies

![](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/Normalization/pics/20.png)

### Requirements for Good normalized set of tables

* Evaluate PK assignments and naming conventions 
* Refine attribute atomicity
  * Atomic attribute: Cannot be further subdivided
  * Atomicity: Characteristic of an atomic attribute
* Identify new attributes and new relationships
* Refine primary keys as required for data granularity
  * Granularity: Level of detail represented by the values stored in a table's row
* Maintain historical accuracy and evaluate using derived attributes

### Summary

* 1NF: eliminate repeating groups \(partial:y, transitive:y\)
* 2NF: eliminate redundant data \(partial:n, transitive:y\)
* 3NF: eliminate fields not dependent on key fields \(partial:n, transitive:n\)

## Denormalization

* Design goals
  * Creation of normalized relations
  * Processing requirements and speed 
* Number of database tables expands when tables are decomposed to conform to normalization requirements
* Joining a larger number of tables:
  * Takes additional input/output operations and processing logic 
  * Reduces system speed.
* Defects in unnormalized tables 
  * Data updates are less efficient because tables are larger 
  * Indexing is more cumbersome
  * No simple strategies for creating virtual tables known as views. 

