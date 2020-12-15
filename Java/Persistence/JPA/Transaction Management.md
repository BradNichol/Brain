# Transaction Management

Transactions help to keep data in a consistent state, by grouping a series of operations that will either succeed or
fail together. If successful, the transaction will be committed, if unsuccessful, any change will be rolled back automatically.

There are different ways to manage transactions. Below is an example of how this is performed using the
EntityTransaction implementation of EntityManager.

 
```
    public void updateEntity(Entity entity) {
        EntityTransaction entityTransaction = entityManager.getTransaction();
        entityTransaction.begin();
        Entity entity1 = getEntityById(entity.getId());
        entity1.setEntityDescription(entity.getDescription());
        entityManager.flush();
        entityTransaction.commit()
    }

```
{% hint style="info" %}
Please note, the above implementation is often replaced by using [Java Transaction API (JTA)](../JTA/README.md) and applied using
the @Transaction annotation. 
{% endhint %}