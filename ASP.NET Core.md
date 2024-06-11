## Controller Class
>> It is a class that handles incoming http requests and generates responses. Controller class is responsible for processing incoming requests and operate on the data and and returning the results.

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

## [FromBody]

## [Key]

## [DatabaseGenerated]

## Program.cs File
> (1) Entry point of the ASP.NET Core application
> (2) Configuring Entity Framework for database access:
    - Sets up the DbContext to interact with the database.
    - Configures the connection string and database provider (e.g., SQL Server).
> (3) Adding custom services and repositories for dependency injection:
    - Registers services and repositories in the dependency injection (DI) container.
    - Ensures that dependencies are resolved automatically throughout the application.
> (4) Configuring JWT Authentication for securing the API:
    - Sets up authentication schemes and token validation parameters.
    - Ensures secure access to API endpoints through JWT tokens.
> (5) Build and runs the application, configuring the HTTP request pipeline.

## appsettings.json File

## ApplicationDbContext.cs File
> In this file ApplicationDbContext class extends base class named DbContext.
```csharp
            // Below is a Constructor for ApplicationDbContext class. Here DbContextOptions<ApplicationDbContext> is a generic parameter that provides configuration options for the ApplicationDbContext.
            // The DbContextOptions is a class that holds all configuration options. This options include connection string, database provider and other settings that are required for the Entity Framework Core to connnect and interact with the database.

            public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options)
            {

            }
```
> `` : base(options) `` - This line in above snippet is the call to the base class constructor. This ensures that the base class (DbContext) is initialized with the configuration options provided.

> In ASP.NET Core, the ApplicationDbContext is typically registered with the dependency injection (DI) system in the Program.cs file.

> When the framework creates an instance of ApplicationDbContext, it injects the DbContextOptions into the constructor. This is made possible through dependency injection.

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

## Migration in .NET Framework Core :
>> Add-Migration Initial
>> Update-Database