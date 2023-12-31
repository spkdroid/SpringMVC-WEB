# SpringMVC Helloworld


**Step 1: Set Up the Project**

1. Create a new Spring Boot project using Spring Initializer or your favorite integrated development environment (IDE).

2. Add the "Spring Web" dependency to your project. This dependency includes everything you need to build a basic Spring MVC application.

**Step 2: Create a Controller**

In Spring MVC, a controller handles HTTP requests and returns an HTTP response. Create a simple controller by following these steps:

```java
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class HelloWorldController {
    @RequestMapping("/hello")
    @ResponseBody
    public String helloWorld() {
        return "Hello, World!";
    }
}
```

The `@Controller` annotation marks this class as a Spring MVC controller. The `@RequestMapping` annotation maps the `/hello` URL path to the `helloWorld` method, which returns a simple message.

**Step 3: Configure Your Application**

Spring Boot will handle most of the configuration for you. However, you can customize your configuration by creating a `src/main/resources/application.properties` file with the following content:

```
spring.mvc.view.prefix=/WEB-INF/views/
spring.mvc.view.suffix=.jsp
```

This configuration specifies that your JSP views will be located in the `/WEB-INF/views/` directory and have the `.jsp` extension.

**Step 4: Create a JSP View**

Create a JSP (JavaServer Pages) view for displaying your "Hello, World!" message. In your project, create a directory structure like this: `src/main/webapp/WEB-INF/views/`.

Inside the `views` directory, create a file named `hello.jsp` with the following content:

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Hello, World!</title>
</head>
<body>
    <h1>${message}</h1>
</body>
</html>
```

**Step 5: Run Your Application**

You can run your Spring Boot application using your IDE or by running the JAR file generated by Spring Boot.

Access your "Hello, World!" message by navigating to `http://localhost:8080/hello`.
