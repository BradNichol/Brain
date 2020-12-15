# Java Transaction API (JTA)

JTA is an api for managing transactions in Java, it allows you to start, commit and rollback 
transactions seamlessly.

JTA works with JPA so that we don't have to programmatically manage a transaction. We just need to add the @Transactional
annotation to the class or method.

``` 
    @Transactional
    @Repository
    public class EntityDAO {
        //implementation
    }
```

With this annotation applied, Spring creates a proxy for the class which allows it to inject transactional
logic before and after a particular persistence method is invoked.