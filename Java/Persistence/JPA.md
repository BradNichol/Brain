# Java Persistence API (JPA)

## What is JPA?
Persistence in Java can be achieved with the Java Persistence API (JPA) which is a specification for the persistence
of Java objects to any **relational** datastore.

JPA is an abstraction on top of Java database connectivity (JDBC). 

In layman's terms:

- JDBC is a standard for Database Access
- JPA is a standard for ORM

JPA is a specification, and by itself cannot perform any actions. To be functional, JPA requires an implementation,
also known as a persistence provider.

## Persistence Providers
The main implementations available are:

    1. EclipseLink
    2. [Hibernate](https://hibernate.org/)
    3. OpenJPA
    4. Data Nucleus

Of those listed the one I will be learning more about is Hibernate.

{% hint style="info" %}
Spring Data JPA uses Hibernate as its persistence provider.
{% endhint %}

## JPA Metadata
Persistence metadata is required to map between Java objects and database tables. The JPA provider will use the
metadata to perform the correct database operations.

There are two ways to define this metadata.

    1. Annotations within the class
    2. External XML file
    
The popular way is typically via annotations.

{% hint style="info" %}
You can use both annotations and XML files, but note that XML will take precedence.
{% endhint %}

### Annotations
The annotations that you'll find in most Entity classes are:

    1. @Entity
    2. @Table
    3. @Id
    4. @GeneratedValue
    5. @Column

