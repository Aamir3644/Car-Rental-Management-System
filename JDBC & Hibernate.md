## JDBC :
>> Java Database Connectivity
>> is a java API to connect and execute the query with the database.
>> part of the Java SE - Standard Edition
>> it uses JDBC drivers to connect with the database.
>> java.sql package contains classes and interfaces for JDBC API
>> *some popular interfaces*  : Driver, Connection, Statement, PreparedStatement, CallableStatement, ResultSet
>> *some popular classes* : DriverManager

## JDBC Drivers :
>> is a software component that enables java application to interact with the database
>> There are four types of JDBC drivers : 1) JDBC-ODBC Bridge Driver (Type 1 Driver)
                                          2) Native Driver (Type 2 Driver)
                                          3) Network Protocol Driver (Type 3 Driver)
                                          4) Thin Driver (Type 4 Driver)
1) JDBC-ODBC Bridge Driver  >  uses ODBC driver to connect to the database
                            >  converts JDBC method calls into the ODBC function calls
                            >  In Java 8,  it has been removed
2) Native Driver >  uses a database-specific API provided by the database vendor
                 >  partially platform-dependent because they rely on a native library to interact with the database.
3) Network Protocol Driver >  uses a database-independent, network-based protocol to connect to the database server.
                           >  entirely Java-based 
                           >  converts JDBC calls into a protocol that is understood by a middleware server, which then     communicates with the database server
4) Thin Driver >  are fully Java-based and connect directly to the database server using a database-specific protocol
               >  no external dependencies
               >  are often considered the most efficient and suitable for production use because they eliminate the need for middleware layers.

*Statement Interface Methods :* 
public ResultSet executeQuery(String sql): is used to execute SELECT query. It returns the object of ResultSet.
public int executeUpdate(String sql): is used to execute specified query, it may be create, drop, insert, update, delete etc.


## HTTP Methods :

*GET vs POST* : 
>> GET is primarily used for requesting data from a specified resource on the server. It is a safe method meaning it should not have any side effects on the server or data. GET requests typically append data to the URL as query parameters. Data is visible in the URL, which makes it less secure and suitable for small amounts of non-sensitive data.
>> POST is used to submit data to the server to be processed, often for creating new resources. Unlike GET, POST requests can have side effects on the server or data. POST requests send data in the request body, which is not visible in the URL. This allows for sending larger amounts of data, including sensitive information, in a more secure manner.

*PUT vs PATCH* :
>> PUT is used to update a resource or create it if it doesn't exist.
When you send a PUT request, you typically send the entire representation of the resource in the request body. The server then replaces the existing resource with the new representation provided in the request. 
>> PATCH is used to apply partial modifications to a resource. In a PATCH request, you send a representation of the resource with only the changes that need to be applied. The server then applies these changes to the existing resource, leaving the unchanged parts intact.

## What is Session ?
>> Session is a conversional state between client and server and it can consists of multiple request and response
between client and server. Since HTTP and Web Server both are stateless, the only way to maintain a session is
when some unique information about the session is passed between server and client in every request and
response.

## What is Servlet ?
>> A Servlet is a Java-based server-side component used in web application development. Servlets extend the functionality of web servers by handling incoming HTTP requests and generating dynamic responses.They are commonly used to create dynamic web pages by generating HTML, JSON, XML, etc. 

## What is a Web Container or Servlet Container ?
>> is nothing but server side JVM. It is a server side component of a web server that manages the execution of web components. it provides runtime environment for dynamic web components like sevlet ,jsp etc.The primary function of a Web Container is to receive and process HTTP requests, manage the lifecycle of Servlets, and generate responses to be sent back to clients.

--------------------------------------------------------------------------------------------------------------------------------

## What is JSON ?
>> it stands for JavaScript Object Notation. JSON is a standard format or data interchange format that uses human-readable text and it is in key-value pairs. It is used for transmitting data between client and server.

## What is Maven ? 
>> Maven is a widely-used build automation and project management tool for Java (and other) projects. It automates tasks like compiling, testing, and packaging, simplifies dependency management. Developers declare project details in a pom.xml file, and Maven handles the rest, including fetching dependencies from a central repository.

## What is JPA ?
>> The Java Persistence API (JPA) is a specification of Java. It is used to persist data between Java object and relational database.
As JPA is just a specification, it doesn't perform any operation by itself. It requires an implementation. So, ORM tools like Hibernate implements JPA specifications for data persistence. It defines how you can map an entity to a table, it defines how you can perform operations on your entities.
The *javax.persistence* package contains the JPA classes and interfaces.

## What is Hibernate
>> Firstly, Hibernate is a Imlementation of JPA specification. Hibernate is a ORM framework that simplifies database interaction in Java applications, offering features like database independence, automatic table generation, and query generation. It simplifies working with the relational databases, allowing developers to focus on their application logic while Hibernate takes care of the underlying data access tasks.
>> ORM stands for Object-Relational Mapping. It is a programming technique and a framework that allows developers to interact with relational databases in an object-oriented manner. ORM frameworks provide a way to map Java or other programming language objects to database tables. Each object class corresponds to a table, and object attributes map to table columns. Developers can work with objects and classes rather than writing raw SQL queries. The ORM framework generates the necessary SQL statements to interact with the database, such as SELECT, INSERT, UPDATE, and DELETE queries.

## What can you tell about Hibernate Configuration File ?
>> Hibernate Configuration File or hibernate.cfg.xml is one of the most required configuration files in Hibernate. By default, this file is placed under the src/main/resource folder.
The file contains database related configurations and session-related configurations.

## What are the advantages of Hibernate over JDBC ?
>> Clean Readable Code: Using hibernate, helps in eliminating a lot of JDBC API-based boiler-plate codes, thereby making the code look cleaner and readable.
>> HQL : Hibernate provides HQL which is closer to Java and is object-oriented in nature. This helps in reducing the burden on developers for writing database independent queries. In JDBC, this is not the case. A developer has to know the database-specific codes.
>> Transaction Management: JDBC doesn't support implicit transaction management. It is upon the developer to write transaction management code using commit and rollback methods. Whereas, Hibernate implicity provides this feature.
>> Hibernate supports OOPs features like inheritance, associations and also supports collections. These are not available in JDBC.

## Connection Pooling :
>> Connection Pool is a pool of already created connection objects which are ready to use. If we want to communicate with database then we request the Connection Pool to provide Connection. By using that connection we can communicate with the database. After the work, connection will be returned to pool rather than destroying. Hence we can use same connection object multiple times, so that overall performance will be improved.


## What is Session in Hibernate ?
>> A session is an object that maintains the connection between Java object application and database. Session also has methods for storing, retrieving, modifying or deleting data from database using methods like persist(), load(), get(), update(), delete(), etc.
>> A Hibernate session is responsible for managing the lifecycle of persistent objects. It tracks changes made to Java objects and synchronizes them with the database when necessary.
>> Session Object is associated with L1 cache.
>> Session is not a thread-safe object which means that any number of threads can access data from it simultaneously.

## What is Session Factory :
>> It is a Factory(provider) of session objects.
>> we use SessionFactory object to create session object.
>> It is immutable that means Once SessionFactory is created, any changes made to hibernate.cfg.xml will not be auto reflected in SessionFactory.
>> It is associated with L2 cache.

## Hibernate Cache Types :
>> First-Level Cache (Session Cache):

- The first-level cache is associated with a Hibernate Session and is enabled by default.
- It stores objects that have been queried or manipulated within the current session.
- The first-level cache ensures that if you retrieve the same object multiple times within a session, it's fetched from memory rather than the database. 

>> Second-Level Cache:

- The second-level cache is shared among multiple sessions within the same application.
- It stores data in a global cache, typically an external caching provider.
- Second-level caching is useful for caching data that is frequently accessed across different sessions.

## Lazy Loading & Eager Loading :
>> Lazy Loading:
Lazy loading is a technique used in database access and Object-Relational Mapping (ORM) frameworks like Hibernate. With lazy loading, data is loaded from the database only when it's explicitly requested. This minimizes resource usage and improves performance by fetching data on-demand.

>> Eager Loading:
Eager loading is the opposite of lazy loading. In eager loading, data is loaded from the database immediately, along with the main entity. This approach ensures that all related data is available upfront, reducing the need for additional database queries. Eager loading is useful when you consistently require the associated data along with the main entity, but it can lead to increased resource consumption when dealing with complex relationships.

## Lazy Loading regarding load() : 
>> You can use the load() method to retrieve an entity by its primary key.
-  The object returned by load() is a proxy object or a "placeholder" for the real entity.
   It behaves like the real entity, but it doesn't fetch data from the database until necessary.
   If you never access the proxy object's data, Hibernate avoids the database query altogether, which can be a significant performance optimization.
-  When you load an entity using load(), Hibernate initializes the entity's attributes, but it delays the loading of associated entities (e.g., collections or other entities referenced by relationships) until you explicitly access them.
  `` Author author = bookProxy.getAuthor(); `` // Associated Author entity is loaded here 


## Lazy Initialization Exception : 
>> Lazy loading works as long as the Hibernate session that fetched the data is still open.To access lazily loaded data successfully, you need to ensure that the associated Hibernate session is still open when you access the data.
If you attempt to access the data when the session is closed or no longer available, Hibernate cannot retrieve the data from the database, leading to a LazyInitializationException.


## Default Behaviour regarding Loading  in Hibernate : 
>> The default behavior is to load ‘property values eagerly’ and to load ‘collections lazily’. Contrary to what you might remember if you have used plain Hibernate 2 (mapping files) before, where all references (including collections) are loaded eagerly by default.
- @OneToMany and @ManyToMany associations are defaulted to LAZY loading; and
@OneToOne and @ManyToOne are defaulted to EAGER loading. 

## Hibernate Entity LifeCycle States :
>> 1) Transient
   2) Persistent or Managed
   3) Detached
   4) Removed

1) Transient : 
                Transient entities exist in heap memory as normal Java objects. Hibernate does not manage transient entities. 
                In simple words, a transient entity has neither any representation in the database nor in the current Session.
2) Persistent :
                A persistent entity is mapped to a specific database row, identified by the ID field. Hibernate’s current running Session is responsible for tracking all changes done to a managed entity and forwarding these changes to database.
> We can get persistent entity in either of two ways:
- Load the entity using get() or load() method.
- Persist the transient or detached entity using persist(), save(), update() or saveOrUpdate() methods.

3) Detached :
                Detached entities have a representation in the database but these are currently not managed by the Session. Any changes to a detached entity will not be reflected in the database, and vice-versa.
                A detached entity can be created by closing the session that it was associated with, or by evicting it from the session with a call to the session’s evict() method.
> In order to make a persistent entity from a detached entity, the application must re-attach it to a valid Hibernate Session. A detached instance can be associated with a new Hibernate session when your application calls one of the load(), refresh(), merge(), update(), or save() methods on the new session with a reference to the detached object.
After the method call, the detached entity would be a persistent entity managed by the new Hibernate session.

4) Removed :
                Removed entities are objects that were being managed by Hibernate (persistent entities, in other words) and now those have been passed to the session’s remove() method.
                When the application marks the changes held in the Session as to be committed, the entries in the database are deleted.


## What is Dirty Checking ?
>>  When an entity is attached to a Hibernate session, Hibernate monitors the changes made to its properties, and when a transaction is committed, it automatically generates SQL UPDATE statements to persist those changes to the database. This process is sometimes referred to as "dirty checking" because it identifies which fields or properties of an entity are "dirty" or have been modified.

