# Entity Manager

The Entity Manager API is used to create, uodate, remove and find entity instances. 

Entities are managed by the Entity Manager and until an entity is managed it is considered to 
be a Plain Old Java Oject (POJO), in detached state.

Once it's managed, it is now in a managed state.



***Notes to be updated regarding Entity Manager***

## Application Layers

A typical structured layer for persisting objects is as follows:

1. Controller - Handles incoming request
2. Service - Interacts with DAO and applies business logic
3. DAO - Final layer that communicates with the DB to persist the entity.

