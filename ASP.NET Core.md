## What is the Code Workflow in .NET ?
- Firstly C#, F# code is converted to Common Intermediate Language (CIL) by the help of Native Compiler.
- Compiled code is stored in the form of .DLL (Dynamic Link Library) or .EXE file extension.
- When the .NET application runs, Common Language Runtime (CLR) takes the assembly file and converts the CIL into machine code with the help of the Just In Time(JIT) compiler.
- Now, this machine code can execute on the specific architecture of the computer it is running on.
- CLR manages garbage collection, type safety, exception handling, etc.
- CIL Code is called as managed code.

## What is a garbage collector?
- Garbage collector reclaims the memory from object that are no longer in use. The memory heap is partitioned into 3 generations:

> Generation 0: It holds short-lived objects.
> Generation 1: It stores medium-lived objects.
> Generation 2: This is for long-lived objects.
- Collection of garbage refers to checking for objects in the generations of the managed heap that are no longer being used by the application.

## MVC (Model View Controller)
- **Model** : Model represents the data and the rules related to it. It is responsible for retriving data from database and processing it.
- **View** : View is the user interface of the application. It displays data to the user and sends user inputs to the controller.
- **Controller** : The controller acts as an middleman between the model and view. It handles user inputs, process it and sends response.

## Depedency Injection 
- Dependency Injection is a design pattern in which instead of a class creating it own dependencies, they are provided to the class by an external entity.
- This ables us to achieve loose coupling.
- In software, a loosely coupled design means you can easily change, test, or replace parts of your application without needing to understand or modify other parts. This leads to more robust, flexible, and maintainable systems.

## Kestrel
- Kestrel is a lightweight web server used for hosting.
- Kestrel is essential for handling HTTP requests in your .NET Core project. It listens for incoming requests and communicates them to your application.

## IIS (Internet Information Services)
- IIS is a web server which is also used for hosting. But it is not open source like Kestrel. Also It does not have Cross Platform Compatibility.

## Middleware
- Middleware components are used to process requests and responses in the request pipeline. They can perform tasks like authentication, routing, and logging.

## Entity Framework Core
- EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects, eliminating much of the data-access code they would usually need to write.

## Entity Framework Core Migrations
>> Add-Migration Initial
>> Update-Database

## Different Types of Service in .NET Core Depedency Injection
- Transient Service 
> Transient services are created each time they are requested. This is suitable for stateless services that do not hold any state between requests.

- Scoped Service
> Scoped services are created once per request. They are suitable for services that should maintain state within a single request but not across requests.

- Singleton Service
> Singleton services are created once and shared throughout the application's lifetime. This is suitable for services that maintain state and are safe to be used by multiple requests concurrently.

## CORS (Cross Origin Resource Sharing)
- CORS is a security feature that controls which origins can access a web resource. You can configure CORS policies in the Program.cs to allow or restrict cross-origin requests based on specific rules.

## Program.cs File
- (1) Entry point of the ASP.NET Core application
- (2) Configuring Entity Framework for database access:
    - Sets up the DbContext to interact with the database.
    - Configures the connection string and database provider (e.g., SQL Server).
- (3) Adding custom services and repositories for dependency injection:
    - Registers services and repositories in the dependency injection (DI) container.
    - Ensures that dependencies are resolved automatically throughout the application.
- (4) Configuring JWT Authentication for securing the API:
    - Sets up authentication schemes and token validation parameters.
    - Ensures secure access to API endpoints through JWT tokens.
- (5) Build and runs the application, configuring the HTTP request pipeline.

## appsettings.json File
- appsettings.json is a configuration file used in .NET Core and ASP.NET Core applications to store application settings. This file is a JSON-formatted text file that can include various configuration settings, such as connection strings, logging settings, and other application-specific settings.

## launchSettings.json
- You can set the environment variables in this file. 
- For example, you can set development or production environment in this file.

## ApplicationDbContext.cs File
- In this file ApplicationDbContext class extends base class named DbContext.
```csharp
            // Below is a Constructor for ApplicationDbContext class. Here DbContextOptions<ApplicationDbContext> is a generic parameter that provides configuration options for the ApplicationDbContext.
            // The DbContextOptions is a class that holds all configuration options. This options include connection string, database provider and other settings that are required for the Entity Framework Core to connnect and interact with the database.

            public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options)
            {

            }
```
- `` : base(options) `` - This line in above snippet is the call to the base class constructor. This ensures that the base class (DbContext) is initialized with the configuration options provided.

- In ASP.NET Core, the ApplicationDbContext is typically registered with the dependency injection (DI) system in the Program.cs file.

- When the framework creates an instance of ApplicationDbContext, it injects the DbContextOptions into the constructor. This is made possible through dependency injection.

## Controller Class
- It is a class that handles incoming http requests and generates responses. Controller class is responsible for processing incoming requests and operate on the data and and returning the results.

## ControllerBase 
>> ControllerBase is a Base Class which should be inherited by a controller class in ASP.NET Core Web API Project. This Base Class provides the core functionalities needed to handle HTTP requests.

## [ApiController]
>> ApiController is a attribute to apply to your controller class. This attribute makes the controller a Web API controller and enables several conventions and behaviors.

## [Route] 
>> Route attribute is used to map the incoming http requests to your controller actions. It specifies the url pattern that should be matched to execute a particular action in your controller.

(1) Controller Level Route :  Applied to the controller class, it defines the base route for all actions within that controller.
-[Route("/api/[controller]")]

(2) Action Level Route :  Applied to the action level methods, it defines the specific route patterns for those actions.
- [HttpGet], [HttpPost], [HttpPut], [HttpDelete] are Action Level Routes.
- [HttpGet("details")]

## DbContext Class
>  DbContext class is a central part of the Entity Framework Core. It acts as a bridge between your application and database.It manages database connections and is responsible for querying and saving data.
> It configures how the application connects to and interacts with the database using DbContextOptions.
> It tracks changes to entities, Provides methods to save changes to the database. (methods like SaveChanges and SaveChangesAsync.)

## DbSet<Model_Name>
> DbSet<T> maps to a table in the database.
> DbSet<T> manages the collection of all the entities in the context of a given type T.
> It offers different methods to perform CRUD operations. (methods like Add(), Remove(), Find(), Update(), FirstOrDefault())

## OnModelCreating(ModelBuilder modelBuilder)
>> OnModelCreating() is a method in Entity Framework Core that is used to configure the model that is being created for the context.
>> It is part of the DbContext class and is overridden to customize the entity configurations using the Fluent API. 
>> This method is crucial for defining relationships, setting up the primary keys and doing other configurations that are not possible through data annotations.

>> Fluent API:
- The Fluent API provides a more comprehensive way to configure the model compared to data annotations. It uses method chaining to configure entities and their properties.

>> ModelBuilder:
- The ModelBuilder parameter passed to the OnModelCreating method is used to configure entities. It provides various methods to configure entities and their relationships.
