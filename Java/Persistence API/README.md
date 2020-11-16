# Persistence API

## What is persistence?
Persistence refers to information that continues to exist even after the process or application that created it is
no longer running.

Data that is stored in memory is usually destroyed when the application shuts down, unlike persisted data that is 
stored across time and can live independent of the system that created it.

We persist data so that later it can be:

- Retrieved
- Processed
- Transformed
- Analyzed

**Storage options to persist data**

- Relational databases
- NoSQL databases
- File systems
- etc

## What is the Java Persistence API?
Persistence in Java can be achieved with the Java Persistence API (JPA) which is a specification for the persistence
of Java objects to any **relational** datastore.

