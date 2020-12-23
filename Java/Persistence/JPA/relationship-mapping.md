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
In this relationship two entities can reference each other, but also other entities too. 

For example, a company can associate with many different freelance workers, and freelancers can associate
with many different companies. 

## Join Types
There are two ways to join the information across tables, using @JoinColumn and @JoinTable.

When using @JoinColumn, typically in many-to-one relationships, the two columns across two tables will store 
the same reference (id). For example, the id column on Company table will store in the company_id column
on the Employee table, thus linking the employee record with the company.

When using @JoinTable, typically in many-to-many relationships, a third table is generated that stores
the linking id's. For example:

| id | company_id | employee_id |
| ---| ---------- | ----------- |
| 01 | 00001 | 00056 |
| 02 | 00001 | 00045 |
| 03 | 00001 | 00123 |
| 04 | 00002 | 001323 |

When the data is required this table will be referenced to join the correct records.

**Which one should I use?**
This will depend on the use case. Please note that JoinColumn is typically more performant as a third table
is not required to process data. So if JoinColumn is sufficient for the use case then this should be used.