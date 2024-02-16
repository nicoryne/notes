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


