# Ch2. Data Models

* Entity: Unique and distinct object used to collect and store data
* Attribute: Characteristic of an entity
* Relationship: Describes an association among entities
  * One-to-many \(1:M\)
  * Many-to-many \(M:N or M:M\)
  * One-to-one \(1:1\)
* Constraint: Set of rules to ensure data integrity

### Standard Database Concepts

* Schema 
  * Conceptual organization of the entire database as viewed by the database administrator 
* Subschema 
  * Portion of the database seen by the application programs that produce the desired information from the data within the database
* Data manipulation language \(DML\) 
  * Environment in which data can be managed and is used to work with the data in the database Schema 
* data definition language \(DDL\) 
  * Enables the database administrator to define the schema components

### The Relational Model

Produced an automatic transmission database that replaced standard transmission databases 

* Based on a relation Relation or table: 
  * Matrix composed of intersecting tuple and attribute 
    * Tuple: Rows 
    * Attribute: Columns 
* Describes a precise set of data manipulation constructs

Advantages:

* Structural independence is promoted using independent tables 
* Tabular view improves conceptual simplicity 
* Ad hoc query capability is based on SQL 
* Isolates the end user from physical-level details 
* Improves implementation and management simplicity

Relational Database Management System\(RDBMS\)

* Performs basic functions provided by the hierarchical and network 
* DBMS systems Makes the relational data model easier to understand and implement 
* Hides the complexities of the relational model from the user

![](../.gitbook/assets/image.png)



