# Run Unit Tests Faster

By default, JUnit tests are run sequentially in a single thread. 

Using an experimental feature, JUnit 5.3 provides the ability to run tests in parallel to speed up test execution. Parallelism will be equal to the number of available processors/cores.

### Configure JUnit

Create a file called `junit-platform.properties` in `src/test/resources` with the following contents:

```shell
junit.jupiter.execution.parallel.enabled = true
```

### Annotate test methods

Add the annotation `@Execution(ExecutionMode.CONCURRENT)` to test methods.

```java  
/**
 * Get user by username.
 */
@Test
@Execution(ExecutionMode.CONCURRENT)
public void getUserByUsername_ValidUsername_ShouldLoadSuccessfully() {
    User user = userDao.findByUsername("tedbaker");
    assertNotNull(user);
}

/**
 * Get user by email.
 */
@Test
@Execution(ExecutionMode.CONCURRENT)
public void getUserByEmail_ValidEmail_ShouldLoadSuccessfully() {
    User user = userDao.findByEmail("ted.baker@orbiks.com");
    assertNotNull(user);
}
```

The above tests should be run in parallel on a multi-core system.

Alternatively, rather than annotating tests methods you can annotate the test class with `@Execution(CONCURRENT)` to run all tests cases in parallel.

See [JUnit Parallel Execution](https://junit.org/junit5/docs/current/user-guide/#writing-tests-parallel-execution) for more details.

