# Data Model and ERD

## E-R Model Constructs

- Entities
    - Entity instance: person, place, object, event, concept 
        - *often corresponds to a row in a table.*
    - Entity Type: collection of entities
        - *often corresponds to a table.*

- Relationships
    - Relationship instance: link between entities
        - *corresponds to primary key-foreign key equivalancies in related tables.*
    - Relationship type: category of relationship
        - *link between entity types*

### Sample E-R Diagram
![Alt text](https://image.slidesharecdn.com/moderndatabasemanagement-jeffreya-hoffermaryb-prescott-110301060446-phpapp01/75/modern-database-management-jeffrey-a-hoffer-mary-b-prescott-77-2048.jpg?cb=1666223644 "erdiagram")

### Basic E-R Notation
![Alt text](https://image.slidesharecdn.com/moderndatabasemanagement-jeffreya-hoffermaryb-prescott-110301060446-phpapp01/75/modern-database-management-jeffrey-a-hoffer-mary-b-prescott-78-2048.jpg?cb=1666223644 "basicernotation")

## What should an Entity be?

- Should be:
    - An object that will have many instances in the database
    - An object that will be composed of multiple attributes
    - An object that we are trying to model

- Should NOT be:
    - A user of the database system
    - An output of the database system 

## Attributes

> property or characteristic of an entity or relationship type

| Classifications |
| :-------------: |
| Required vs. Optional |
| Simple vs. Composite |
| Single-valued vs. Multivalued |
| Stored vs. Derived |
| Identifier |

### Types of Attributes

There are six main types of attributes: Simple Composite, Single-valued, Multi-valued, and Derived.

#### Main Types of Attributes

- Simple Attribute
    - an attribute that cannot be further subdivided into components.
        *Example: The roll number of a student, the id number of an employee*
    
- Composite Attribute
    - an attribute that can be split into components.
        *Example: The address can be further split into house number, street number, city, state, country, and pin code.*

- Single-valued Attribute
    - an attribute which takes up only a single value of each entity instance.
        *Example: The age of a student*

- Multi-valued Attribute
    - an attribute which takes up more than a single value for each entity instance.
        *Example: Phone number of a student can be either landline or mobile*

- Derived Attribute
    - an attribute that can be derived from other attributes.
        *Example: Total and average marks of a student*

#### Other Types of Attributes

- Complex Attribute
    - attributes which can be formed by the nesting of composite and multi-valued attributes.
        *Example: Phone number of a person who owns more than one house, and each house has more than one phone number*

## Identifiers (Keys)

> attribute (or combination of attributes) that uniquely identifies individual instances of an entity type

Candidate Identifier: an attribute that could be a key satisfies the requirements for being an identifier
