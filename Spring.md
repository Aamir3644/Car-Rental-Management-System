## What is Spring ?
>> Spring is a Dependency Injection Framework to make java application loosely coupled which makes JAVA EE application development easier.

## Inversion Of Control :
>> Analogy:
Think of IoC like going to a restaurant. In a traditional, non-IoC scenario, you would cook your own meal at home. You control every aspect of the cooking process, from chopping vegetables to setting the table. It's all on you.
Now, consider going to a restaurant. Here, you are not in control of the cooking process. You don't chop the vegetables or operate the kitchen. Instead, you place an order, specifying what you want to eat, and the restaurant's chef and staff take care of preparing and serving your meal. You are "inverting control" by letting the restaurant manage the cooking process.

IoC in Software Development:
In software development, IoC follows a similar principle. Traditionally, when writing code, you directly create objects, manage dependencies, and control the flow of your program. You are in control of everything.
With IoC, you delegate some of these responsibilities to a container or framework. Here is how it works:
- Dependency Management: Instead of creating objects directly within your code, you declare what your code needs as dependencies. 
- Configuration: You provide configuration details to the IoC container, telling it how to create and wire these dependencies. This can be done through XML files, annotations, or code.
- Container Control: The IoC container takes over. It creates the necessary objects, manages their lifecycles, and injects (provides) them into your code when needed. You do not have to worry about when and how these objects are created or how they interact.

## Dependency Injection :

## IoC Container :


## What is the difference between Spring and Spring Boot ?
>> Spring is a comprehensive framework for building Java-based enterprise applications. It offers a collection of modules and tools that address various aspects of application development.Spring provides flexibility but requires developers to configure many aspects of the application manually.
>> Spring Boot, on the other hand, is an extension of the Spring framework designed to simplify and accelerate the development of Spring-based applications. It provides default configurations, auto-configuration, and embedded servers, reducing the need for extensive XML configuration.
Examples : 
          - Spring is like a toolbox with various tools that you can use to build a Java application. However, it requires you to configure and set up many things manually.
          - Spring Boot, on the other hand, is like a pre-assembled toolkit. It takes care of a lot of the setup and configuration for you, so you can get started quickly. It's like having a default set of tools ready to use out of the box. 
    
## 