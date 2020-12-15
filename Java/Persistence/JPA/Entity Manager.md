# Entity Manager

The Entity Manager API is used to create, uodate, remove and find entity instances. 

Entities are managed by the Entity Manager and until an entity is managed it is considered to 
be a Plain Old Java Oject (POJO), in detached state.

Once it's managed, it is now in a managed state.



***Notes to be updated regarding Entity Manager***

## Application Layer

You'll typically find the entity manager usage, or other persistent functionality in the DAO or repository
layers/classes.

## Using the Entity Manager

### Reading Entities
When retrieving an entity using JPA, it's the entity manager that performs this operation, using the available 
**find** method. There are several variations on the find method, but typical it is used with an entity's primary key.

```
    public Entity getEntityById(String entityId) {
        return entityManager.find(Entity.class, entityId);
    }
```

### Persisting Entities
To persist an entity, use the available **persist** method.

```
    public void addEntity(Entity entity) {
        entityManager.persist(entity);
    }

```

### Updating Entities
Note, there is no specific update method to call in the entity manager class, an update happens when one of the
entities attribute values changes.

First you use the find method to return the persisted entity, and then you update its values before re-persisting.

```
    public void updateEntity(Entity entity) {
        Entity getEntity = getEnityById(entity.getId());
        getEntity.setName(entity.getName());
        entityManager.flush();
    }

```

### Deleting Entities
To delete an entity, use the available **remove** method.

```
    public void deleteEntity(String entityId) {
        entityManager.remove(getEntityById(entityId));
    }

```