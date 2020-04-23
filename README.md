# Testcontainers
![Sweet](https://d33wubrfki0l68.cloudfront.net/a661dbbe55be3e9cb77889f24835a44c6daf53c2/ce0aa/logo.png)

For this example we will run an image from Docker Hub (hello-world)
and then assert if the container is running ok

## Usage
```bash
.gradlew test
```
[Checkout this example](src/test/java/testcontainer/sample/LibraryTest.java)

```java
@Testcontainers
class LibraryTest {

    @Container
    private GenericContainer  helloWorld = new GenericContainer<>("hello-world");

    @Test void testSomeLibraryMethod() {
        assertTrue(helloWorld.getLogs().contains("Hello from Docker!"));
    }
}
```
