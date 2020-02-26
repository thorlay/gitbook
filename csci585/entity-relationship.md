# Ch3. Entity Relationship

* ERD depicts the:
  * Conceptual database as viewed by end user
  * Database's main components
    * Entities
    * Attributes
    * Relationships
* Entity - Refers to the entity set and not to a single entity occurrence

## Attributes

* Characteristics of entities 
* Required attribute: Must have a value, cannot be left empty
* Optional attribute: Does not require a value, can be left empty
* Domain-Set of possible values for a given attribute
* Identifiers: One or more attributes that uniquely identify each entity instance
  * An identifier is also called a KEY, or PRIMARY KEY - **this is one of the 'key' concepts in all of database theory!!**

Chen's model and crow's foot model

* In Crow's Foot notation, 'bold' attributes are 'required' \(can't be null\).
* Composite idnetifier: Primary key composed of more than one attribute
* Compound identifier: Attribute that can be subdivided to yield additional attributes.
* Simple attribute: attribute that can not be subdivided
* Single - value attribute : Attribute that has only a single value.
* Multivalued attributes : Attributes that have many values and require creating
* Derived attribute: Attribute whose value is calculated from other attributes

## Relationships

* Association between **entities** that always operate in both directions
* **participants**: Entitles that participate in a relationship
* **Connectivity**: Describes the relationship classification
* **Cardinality** : Expresses the minimum and maximum number of entity occurrences associated with one occurrence of related entity.

### Connectivity vs Cardinality

* Connectivity: 1:1, 1:M or M:N \(three diff ways by which two entities are related\).
* Cardinality: \(min,max\) for 1:1, 1:M or M:N \(eg. 1:1 can have \(1,0\) as its cardinality, 1:M can have \(0,4\) as its cardinality\). Sometimes, min is called 'modality' \(and max is cardinality\). The 'inside' symbols denotes min, and the outside ones, max.

### Existence Dependence\(Entity\)

* existence dependence: Entity exists in the database only when it is associated with another related entity occurrence
* Existence independence: Entity exists apart from all of its related entities, referred to as a **strong entity or regular entity**
* NOTE: Existence independence implies a **strong entity**; but, existence dependence \(alone, ie. by itself\) does NOT imply a **weak entity** \(there needs to be one more condition, based on 'relationship strength', for it to become 'weak'\).

### Weak vs strong relationship

* weak relationship: primary key of the related entity does not contain a primary key component of the parent entity
  * eg. class to course
* Strong relationships: primary key of the related entity contains a primary key component of the parent entity.

### Weak entity

* Condition: 
  * Existence-dependent 
  * has a primary key that is a partially or totally derived from parent entity in the relationship
* Database designer determines whether an entity is weak based on business rules

### Relationship Participation

* optional participation
  * one entity occurrence does not require a corresponding entity occurrence in a particular relationship 
* mandatory participation
  * one entity occurrence requires a corresponding entity occurrence in a particular relationship.

### Relationship Degree

* Indicates the number of entities or participants associated with a relationship
* Unary relationship: Association is maintained within a single entity
  * Recursive relationship : Relationship exists between occurrences of the same entity set.
* Binary relationship: Two entities are associated
* Ternary relationship: Three entities are associated.

## Bridge entities

### Associative Entities

* Also known as composite or bridge entities
* Used to represent an M:N relationship between two or more entities.
* Is in a 1:M relationship with the parent entities 
  * **Composed of the primary key attributes of each parent entity**
* May also contain additional attributes that paly no role in connective process.

## Developing an ER diagram

* Create a detailed narrative of the organization's description of operations
* Identify business rules based on the descriptions 
* Identify main entities and relationships from the business rules 
* Develop the initial ERD
* Identify the attributes and primary keys that adequately describe entities
* Revise and review ERD

