# Spring: Test-Driven Development with JUnit

This course teaches how to test a Spring application at different layers.
The course uses Junit 4, but I use Jnunit 5 in any code representations below.

## Why TDD Matters
* Quick design validation and feedback
* Tests become executable documentation and acceptance criteria
* Change management
* Team member onboarding and training

## Testing Service Components
The service layer is typically the most business logic heavy layer and is where test coverage 
is needed the most.

### Test Planning
Have a plan before writing tests:

1. What features need most coverage?
2. What are the high priority test cases?
3. What type of tests are required? (Unit, Integration, behaviour etc)

### Service Integration Tests
Setup a service integration tests by instructing Junit to do:
* Only load @Service annotations and dependencies
* Connect to required data source
* Don't load unnecessary components such as @RestController

```aidl
@ExtendWith(SpringExtension.class)
@SpringBootTest(webEnvironment = WebEnvironment.NONE)
public class IntegrationTest {
    
    @Autowired
    private SystemUnderTest systemUnderTest; //As a minumum, you'll need to wire in the class you're testing
    
   
    //test
}

The attributes inside the spring boot test annotation make 
sure only required components are loaded.
```

Example test from the course:
```aidl
@ExtendWith(SpringExtension.class)
@SpringBootTest(webEnvironment = WebEnvironment.NONE)
public class ContactManagementServiceIntegrationTest {
    
    @Autowired
    private ContactManagementService systemUnderTest;
    
   
    @Test
    void testAddContactHappyPath() {
        //Create a contact
        CustomerContact aContact = new CustomerContact();
        aContact.setFirstName("T-1000");
        
        //Test adding the contact
        CustomerContact newContact = systemUnderTest.add(aContact);
        
        //Verify
        assertNotNull(newContact); // a good smoke test is initially check the returned data is not null
        assertNotNull(newContact.getId());
        assertEquals("T-1000", newContact.getFirstName()); 
       
    }

```

### Service Unit Tests

When unit testing your methods in a service class, you isolate your testing to that class only and don't need to worry about other
dependencies should as data persistence. To achieve this you'll need to use mocks to 'mock' required dependencies.


```aidl
@ExtendWith(MockitoExtension.class) // this instructs the enviroment to load Mockito for mocking.
@SpringBootTest(webEnvironment = WebEnvironment.NONE)
public class ContactManagementServiceUnitTest {

    @Mock // creates the mock the class
    private CustomerContactRepository customerContactRepository;
    
    @InjectMocks // injects the above mock dependencies into the service
    private ContactManagementService systemUnderTest;
   
    @Test
    void testAddContactHappyPath() {
        
        //Create a contact
        CustomerContact  aMockContact = new CustomerContact();
        aMockContact.setFirstName("T-1000");
        
        // The when statement executes, when the method is called during the test, and returns the mock
        when(customerContactRepository.save(any(CustomerContact.class))).thenReturn(aMockContact);
        
         //Test adding the contact
        CustomerContact newContact = systemUnderTest.add(null); // it doesn't matter that argument you pass, because it will return the mock 
        
        //verify
        assertEquals("T-1000", newContact.getFirstName());     
    }
}

```

## Testing Controller Components

### Test Planning
1. What features need most coverage?
2. What are the high priority test cases?
3. What type of tests are required? (Unit, Integration, behaviour etc)
4. What kind of @Controllers are involved: MVC, RESTful, or both?

{% hint style="info" %}
The main difference between the types of controllers is the output that they send back. MVC returns ViewModel objects, whereas RESTful returns JSON
or XML.
{% endhint %}

The following examples are for MVC controllers.

### Controller Integration Tests
Initial setup preview:
1. Load full web environment
2. Load @Controller
3. Load @Service
4. Load @Repository

```aidl
@ExtendWith(SpringExtension.class)
@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT) // environment now simulates a real web environment, and uses random port to avoid conflicts.
public class ContactManagementControllerIntegrationTest {
    
    @Autowired
    private ContactManagementController systemUnderTest;
    
   
    @Test
    void testAddContactHappyPath() {
        //Create a contact
        CustomerContact aContact = new CustomerContact();
        aContact.setFirstName("T-1000");
        
        // POST our customer contact form bean to the controller
        String outcome = systemUnderTest.processAddContactSubmit(aContact);
        
        
        //Verify
        assertThat(outcome, is(equalTo("success")));
    }
    
    @Test
    void testAddContactFirstNameIsMissing() {
        //Create a contact
        CustomerContact aContact = new CustomerContact();
        
        // POST our customer contact form bean to the controller
        String outcome = systemUnderTest.processAddContactSubmit(aContact);
        
        //Verify
        assertThat(outcome, is(equalTo("failure")));
    }

```
### Controller Unit Tests
Initial setup preview:
1. Mock web browser behaviour
2. Load @Controller
3. Load mocks for @Service


```aidl
@ExtendWith(SpringExtension.class)
@WebMvcTest(ContactsManagementController.class)
public class ContactManagementControllerUnitTest {
    
    @Autowired
    private MockMvc mockMvc;
    
    @MockBean // @MockBean adds mock objects to the Spring application context.
    private ContactManagementService contactManagementService;
    
    @InjectMocks
    private ContactManagementController systemUnderTest;
    
   
    @Test
    void testAddContactHappyPath() thows Exception {
        // setup mock contact 
        CustomerContact mockCustomerContact = new CustomerContact();
        mockCustomerContact.setFirstName("T-1000");
        
        when(contactManagementService.add(any(CustomerContact.class))).thenReturn(mockCustomerContact);
        
        //simulate form bean that would POST from webpage
        CustomerContact aContact = new CustomerContact();
        aContact.setFirstName("T-1000");
        
        // simulate the form submit to POST
        mockMvc
            .perform(post("/addContact", aContact))
            .andExpect(status().isOk()).andReturn();
    }
    
    @Test
    void testAddContactFirstNameIsMissing() {
        //Create a contact
        CustomerContact aContact = new CustomerContact();
        
        // POST our customer contact form bean to the controller
        String outcome = systemUnderTest.processAddContactSubmit(aContact);
        
        //Verify
        assertThat(outcome, is(equalTo("failure")));
    }

```

## Testing Repository Components

### Test Planning
1. What features need most coverage?
2. What are the high priority test cases?
3. What type of tests are required? (Unit, Integration, behaviour etc)
4. What type of persistence layer: relational, graph or both

NOTE: There's not a lot of ROI for unit testing repository as it's the Spring framework that provides alot of what could be called, the units.
The following will focus only on an integration test.

### Repository Integration Test
Initial setup preview:
1. Not load @Controller or @Service
2. Load @Respository and related dependencies
3. Load JPA testing configs
```aidl
@ExtendWith(SpringExtension.class)
@DataJpaTest // shortcut for providing a lot of items to test JPA code. See below
@AutoConfigureTestDatabase(replace=Replace.NONE) // lets us setup a type of database
public class ContactManagementRepositoryIntegrationTest {

    @Autowired
    private TestEntityManager entityManager;
    
    @Autowired
    private ContactManagementRepository systemUnderTest;
    
   
    @Test
    void testFindByEmail() {
        
        // setup data scenario
        CustomerContact aNewContact = new CustomerContact();
        aNewContact.setEmail("theterminator@skynet.com");
        entityManager.persist(aNewContact); // entity manager will add the data to the db
        
        // Find an inserted record
        CustomerContact foundContact = systemUnderTest.findByEmail("theterminator@skynet.com");
        
        // verify
        assertThat(foundContact.getEmail(), is(equalTo("theterminator@skynet.com")));
        
    }
   

```

The @DataJpaTest annotation bundles the following: @AutoConfigureDataJpa, @AutoConfigureTestDatabase, @AutoConfigureTestEntityManager, @Transactional and more.


1. @AutoConfigureDataJpa - imports config needed for JPA testing.
2. @AutoConfigureTestDatabase - Setup for rquired db. Can use embedded, external or staging for example.
3. @AutoConfigureTestEntityManager - Allows direct access to the EntityManager.
4. @Transactional - allows us to have rollback behaviour after test executions.


As with all of the examples above, start with the happy path test scenario and then extend with further test scenarios to ensure you build out
your components in a test driven way.





