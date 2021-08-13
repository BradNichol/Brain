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
* Don't load unnecessary such as @RestController

