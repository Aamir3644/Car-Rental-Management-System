## What is SQL ?
>> SQL stands for Structured Query Language. It is a language used to interact with the database, i.e to create tables, to retrieve data, update or delete data. SQL is an ANSI(American National Standards Institute) standard. 

## What is Database ?
>> A Database is defined as a structured form of data storage in a computer or a collection of data in an organized manner.

select empno, ename from employee
order by empno;

## What does "WHERE" condition do ?
>> Where condition used for searching. Where condition is used to restrict the rows. Searching takes place in Server Hard Disk and then rows are brought into RAM.

## What does "DISTINCT" do ?
>> Whenever you use "DISTINCT", sorting takes place in Server RAM.

## What is Computed Column ?
>> Query -> " select name,salary*12 from employee "
>> So in above query salary*12 is a computed column. Computed column does not save in Hard Disk.
>> It is also called as Pseudo Column, Derived Column, Fake Column.
   
## What is "order by" clause ?
>> Order by clause is used for sorting / presentation purpose. Sorting always happens in RAM.
>> Where clause always comes before order by clause.
>> Order by clause is the last clause in select statement.

## What is alias in SQL ?  
>> you can give alias name to a column while showing output. e.g -> select name, sal*12 as ANNUAL from employee
>> In above Query ANNUAL is alias.
>> Alias will not work in Where Clause, it will give error saying "Unknown Column"
>> Alias will work in Order By Clause.

## What is "Like" ?
>> The "Like" Operator is used in Where clause to search for sepecific pattern in a column.
>  e.g -> select * from emp where ename LIKE "A%"
>> "A%" -> starts with "A"
>> "%A" -> ends with "A"
>> "%A%"-> shows all the rows where ename contains "A"
>> "_A%" -> where second letter is "A"
>> "%L_K%"-> shows all the rows where ename contains "L_K" pattern
>> NOT LIKE "A%" -> not starting with A

## What is ANY and IN Operator ? 
>> In MySQL, IN and ANY Operator is both supported but ANY operator is only supported when you use it with SubQuery.

## What are different types of Commands in SQL ?
``` 
	1) DDL (Data Definition Language)
	-> Create, Drop, Alter, Truncate
	
	2) DML (Data Manipulation Language)
	-> Insert, Update, Delete

	3) DQL (Data Query Language)
	-> Select
	
	4) DCL (Data Control Language)
	-> Grant, Revoke
	
	5) TCL (Transaction Control Language)
	-> Commit, Rollback, Savepoint
```

## Normalization :
>> It is a process used in Database Design used to organize relational database schema effieciently and reduce data redundancy.
>> There are several normal forms like 1NF, 2NF, 3NF, BCNF, 4NF, 5NF, etc. So for any typical database design, First 3 Normal Forms are necessary.
   
1) First Normal Form (1NF) :
	A table is in 1NF, if it does not contain repeating groups or array for any column.
	Each row of table should contain single value.
	
2) Second Normal Form (2NF) :
	A table is in 2NF, if it is in 1NF and all non-prime attributes are fully functionally dependent on the
	primary key.
	In simple terms, there should be no partial dependency on a composite primary key.
	
3) Third Normal Form (3NF) :
	A table is in 3NF if it is in 2NF and there are no transitive dependencies.
	Transitive dependency occurs when a non-prime attribute depends on another non-prime attribute.
	
> For Examples : Refer to Images folder

## Sequence of Clauses in Select Statement :
>>
   1) Where 
   2) Group By
   3) Having
   4) Order By
	
## Internal Working Of Select Statement :
>> Rows are retrieved from Server Hard Disk depending on the where condition to Server RAM
>> Sorting takes place in RAM
>> Then, Grouping is done
>> Then, according to that groups, the group function is performed on each group.
>> if we have Having Clause then it is used for restricting rows from that result column of group function.
>> if we have Order By Clause, it is to be noted that result column of group function can also be used in Order By.
```
e.g :   select job, sum(sal) Addition from emp 
      	where job = 'ANALYST' 	
      	group by job 
      	having Addition > 10000 
      	order by Addition; 
```

## JOINS :
>> Why joins are used : As we know that in database schema, related data is spread across different tables, so when we need to get the related data from different tables then we need to use JOINS.

# Left Join :
```
e.g:  SELECT en.unique_id,e.name FROM Employees e LEFT JOIN EmployeeUNI en ON e.id = en.id 
```
>> In above example, Employees table is driving table(whichever table is associated with "FROM" clause will be the driving table)
>> In Left Join, all the records from left table will be returned in result set and matching records from the right table.
>> In above query, The database engine starts by taking each row from the Employees (driving table)
>> It then looks for a matching row in the EmployeeUNI table (the driven table) based on the id column.
>> If a matching row is found in the EmployeeUNI table, it includes the unique_id from that table in the result.
>> If no matching row is found, it includes NULL for the unique_id.
>> Regardless of whether there is a match or not, it includes the name from the Employees table in the result.

# Right Join :
