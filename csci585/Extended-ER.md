# Extended ER 

- Result of adding more semantic constructs to the original entity relationship model
- EER diagram: Uses the EER model

### Entity supertypes and subtypes

- Entity supertype: generic entity type related to one or more entity subtypes
  - contains common characteristics
- Entity subtype: Contains unque characteristics of each entity subtype
- Criteria to determine the usage
  - There must be different, identifiable kinds of the entity in the user;s environment
  - The different kinds of instances should each have one or more attributes that are unique to that kind of instance.

###  Specialization Hierarchy

- Depicts arrangement of higher-level entity supertypes and lower-level entity subtypes
- Relationships are described in terms of "is-a" relationships
- Subtype exists within the context of a supertype
- Every subtype has one supertype to which it is directly related
- Supertype can have many subtypes.
- Provides the means to:
  - support attribute inheritance
  - Define a special supertype attribute known as the subtype discriminator
  - Define disjoint constraints and complete constraints
  - [image](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/EER/pics/s7.jpg)

### Inheritance

- enables an entity subtype to iinherit sttributes and relationships of the supertype
- all entity subtypes inherit their primary key attribute from their supertype
- At the implementation level, supertype and its subtypes maintain a 1:1 relationship
- Entity subtypes inherit all relationships in which supertype entity participates
- Lower-level subtypes inherit all attributes and relationships from its upper-level supertypes

### Subtype Discriminator

- Attribute in the supertype entity that determines to which entity subtype the supertype occurrence is related
- Default comparison condition is the equality comparison

### Disjoint and Overlapping constraints

- [image](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/EER/pics/s11.jpg)

- Disjoint subtypes: Contain a unique subset of the supertye entity set 
  - Known as nonoverlapping subtypes 
  - Implementation is based on the value of the subtype discriminator attribute in the supertype
- Overlapping subtypes: Contain nonunique subsets of the supertype entity set
  - Implementation requires the use of one discriminator attribute fir each subtype

### Completeness Constraint

- Specifies whether each supertype occurrence must also be a member of at least one subtype
- Types
  - Partial completeness: Not every supertype occurrence is a member of a subtype
  - Total completeness: Every supertype occurrence must be a member of any
- [Specialization Hierarchy Constraint Scenarios](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/EER/pics/s14.jpg)

[Tiny college ERD Using Entity Clusters](http://bytes.usc.edu/cs585/s20_db0ds1ml2agi/lectures/EER/pics/s17.jpg)

