# Ch4. Relational Modeling

## Logical View of data

* relational database model enables logical representation of the data and its relationships.
* logical simplicity yields simple and effective database design methodologies 
* facilitated by the creation of data relationships based on a logical construct called a relation

###  🔑 Keys

* Consist of one or more attributes that determine other attributes 
* Used to :
  * ensure that each row in a table is uniquely identifiable 
  * establish relationships among tables and to ensure the integrity of the data
* **Primary key\(PK\)**: Attribute or combination of attributes that uniquely identifies any given row.

#### Types of Keys

* composite key: Key that is composed of more than one attribute
* Key attribute : Attribute is a part of a key
* Entity integrity: Condition in which each row in the table has its own unique identity
  * All of the values in the primary key must be unique
  * No key attribute in the primary key can contain a null.
* Null: 
  * Absence of any data value that could represent: An unknown attribute value
  * A known, but missing attribute value
  * A inapplicable condition
* Referential integrity: Every reference to an entity instance by another entity instance is valid.

## Keys: many types

* primary \(foreign\) keys are a subset of candidate keys are a subset of superkeys \(note - superkeys could be 'wasteful', ie. contain superfluous, non-needed attrs\)
*  simple keys vs compound keys vs composite keys
* natural keys - keys that are created from real-world entities \(eg. for a US resident, their SSN could be a natural key\)
* surrogate keys \(just make up brand new unique keys\)
* secondary, or 'alternate' keys

You can read a bit more keys [here.](http://www.agiledata.org/essays/keys.html)

### Determination:

* state in which knowing the value of one attribute makes it possible to determine the value of another.
* Is the basis for establishing the role of a key
* Based on the relationships among the attributes

### Dependencies

* Functional dependence: Value of one or more attributes determines the value of one or more other attributes 
  * Determinant : Attributes whose value determines another
  * Dependent: Attribute whose value is determined by the other attribute
* Full functional dependence: Entire collection of attributes in the determinant is necessary for the relationship.

## Relational algebra

Theoretical way of manipulating table contents using relational operator

* Relvar: Variable that holds a relation 
  * heading contains the names of the attributes and the body contains the realtion 
* Relational operators have the property of closure
  * closure: Use of relational algebra operators on existing relations produces new relations

### Operations on table

* select: unary operator that yields a horizontal subset of a table
* project: Unary operator that yields a vertical subset of a table
* union: 
  * combines all rows from two tables, excluding duplicate rows
  * Union-compatible: Tables share the same number of columns, and their corresponding columns share compatible domains
* intersect
  * Yields only the rows that appears in both tables
  * Tables must be union-compatible to yield valid results

### Relational Set operators

* Difference
  * Yields all rows in one table that are not found in the other table
  * Tables must be union-compatible to yield valid results 
* Product
  * Yields all possible pairs of rows from two tables.
* [Join](relational-modeling.md#Types%20of%20Joins) 
  * Allows information to be intelligently combined from two or more table
* Divide 
  * Uses one 2-column table as the dividend and one single-column table as the divisor
  * Output is as single column that contains all values from the second column  of the dividend that are associated with every row in the divisor

### Types of Joins

* Inner join: only returns matched records from the tables that are being joined 
* Outer join: Matched pairs are retained and unmatched values in the other table are left null
  * Left outer join: Yields all of the rows in the first table, including those that do not have a matching value in the second table
  * Right outer join: Yields all of the rows in the second table, including those that do not have matching values in the first table.
* Natural join:
  * A natural join links tables by selecting from two tables, only those rows that have common values for common attributes.
* Left outer Join
  * Output all rows of the left \(CUSTOMER\) table, including ones for which there are no matching values in the join column in the other \(AGENT\) table
* Right outer join
  * Output all rows of the right \(AGENT\) table, including ones for which there are no matching values in the join column in the other \(CUSTOMER\) table.

### Dictionaries \[hold metadata\]

* Data Dictionary: Description of all tables in the database created by the user and designer.
* System catalog: System data dictionary that describes all ojects within the database.
* Homonyms and synonyms must be avoided to lessen confusion
  * Homonym: Same name is used to label different attributes
  * Synonym: Different names are used to describe the same attribute

