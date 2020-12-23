# Relationship Mapping

Entities in a database table will often have a relationship to an entity in another database table. The most common
example of this is the use of a foreign key which can be used to join data across two or more tables.

There are four main relationship (cardinalities) types that can be used to map data across entities, each with a dedicated annotation:

    1. One-to-Many
    2. Many-to-One (@ManyToOne)
    3. One-to-One
    4. Many-to-Many
    
## Relationship Types

### One-To-Many
A one-to-many relationship exists when one row in table A may be linked with many rows in table B, 
but one row in table B is linked to only one row in table A. 

For example an online shopping basket can have many items, so here we have a one-to-many mapping.

### Many-To-One
In this relationship, many entities can relate to a single entity. For example, a Company entity will have many
Employee entities associated to it.

The @JoinColumn annotation in the code below instructs how the relationship is to be mapped. In this case,
join the employee on the company_id and store this in the company_id column.

```
@Entity
public class Employee {

//id and other fields

@ManyToOne
@JoinColumn(name = "company_id")
private Company company;

//constructor

//getters and setters

}

```

### One-To-One
Notes to be updated

### Many-To-Many
Notes to be updated
