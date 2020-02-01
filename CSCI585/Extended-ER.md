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