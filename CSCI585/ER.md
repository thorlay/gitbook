# The Entity Relationship Model (ERM)

- ERD depicts the:
  - Conceptual database as viewed by end user
  - Database's main components
    - Entities
    - Attributes
    - Relationships
- Entity - Refers to the entity set and not to a single entity occurence



## Attributes

- characteristics of entities 
- Required attribute: Must have a value, cannot be left empty
- Optional attribute: Does not require a value, can be left empty
- Domain-Set of possible values for a given attribute
- Identifiers: One or more attributes that uniquely idnetify each entity instance
  - An identifier is also called a KEY, or PRIMARY KEY - **this is one of the 'key' concepts in all of database theory!!**



Chen's model and crow's foot model

- In Crow's Foot notation, 'bold' attributes are 'required' (can't be null).



- Composite idnetifier: Primary key composed of more than one attribute

- Compound identifier: Attribute that can be subdivided to yield additional attributes.

- Simple attribute: attribute that can not be subdivided
- Single - value attribute : Attribute that has only a single value.
- Multivalued attributes : Attributes that have many values and require creating
- Derived attribute: Attribute whose value is calculated from other attributes



## Relationships

- association between entities that always operate in both directions

- **participants**: Entitles that participate in a relationship

- **Connectivity**: Describes the relationship classification

- **Cardinality** : Expresses the minimum and maximum number of entity occurences associated with one occurrence of related entity.





