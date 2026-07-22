![](Images/cover00037.jpeg)

**Cracking the Coding Interview**

**70 Database Questions and Answers**

[Introduction](#part0000.xhtml__Toc430033526)

[Conclusion](#part0000.xhtml__Toc430033527)

[About Author](#part0000.xhtml__Toc430033528)

This book is dedicated to all database programmers.

Copyright © 2015-2035 Chinmoy Mukherjee

All rights reserved. No text of this book may be reproduced in any form or by any electronic or mechanical means, including information storage and retrieval systems, without written permission from the publisher or author, except in the case of a reviewer, who may quote brief passages embodied in critical articles or in a review.

# Introduction

We present 70 interesting database interview questions and answers for readers to practice and crack any database interview. The reader is encouraged to try to solve these questions himself/herself before checking the answers.

Database Interview Question-1. What is “index” used for?

Answer: Index is a lookup table for database records in physical disk. Index makes record searching faster, it is similar to book index. Below figure explains the concept of index pictorially.

![](Images/image00036.jpeg)

Database Interview Question-2. When to not use index?

Answer: Index should not be used for following cases:

· If number of records are small

· If records need to be updated/inserted/deleted on a daily basis

· If column value can be null very often

Database Interview Question-3. What is tempdb?

Answer: tempdb is temporary database which can be used by all users/processes to maintain temporary tables, etc. Content of tempdb is erased when database server is restarted.                                          

Database Interview Question-4. How will you find out all the stored procedures present in a database?    

Answer: SELECT object_name, object_type

FROM  user_objects

WHERE object_type = 'PROCEDURE'

Database Interview Question-5. What are the differences between TRUNCATE and DELETE?

Answer: TRUNCATE removes all rows from a table. The operation cannot be rolled back, also triggers are not executed for TRUNCATE

Database Interview Question-6. What is the difference between IN and EXISTS ?

Answer: EXISTS checks if any such record exists. e.g.

SELECT * FROM Orders o WHERE EXISTS (

    SELECT * FROM Products p where p.ProductNumber = o.ProductNumber)

IN is used to find presence of a record among multiple records. e.g.

SELECT * FROM Orders WHERE ProductNumber IN (1, 10, 100)

Database Interview Question-7. What database parameters can be tuned for performance?" 

Answer: Buffer pool, Log level, etc.

Database Interview Question-8. What is bcp?

Answer: bcp in Sybase helps to copy table into a flat file and vice versa.

Database Interview Question-9. Suppose you are logged onto a database DB1\. What query will you run in DB1 to retrieve data from the table table1 present in another database DB2?      

Answer: We can use either select * from DB2..table1 or use DB2;select * from table1

Database Interview Question-10. What are main   Open source databases?

Answer: PostgreSQL, MySQL, etc.

Database Interview Question-11. What is a View?

Answer: A view is the representation of a SQL statement that is stored in memory so that it can easily be re-used as example

CREATE VIEW [MyProductList] AS

SELECT ProductID,ProductName

FROM Products

WHERE Discontinued=No

SELECT * FROM [MyProductList]

Database Interview Question-12. There is a table “Employee” having two columns – Emp_Name and Office_Locations. Write a query that will display all office locations and the number of employees in each of these locations.

Answer: Select Office_Locations, COUNT(Emp_Name) FROM Employee GROUP BY Office_Locations;

Database Interview Question-13. Write a query to get the employees, who are also managers

Answer: Select name from employees where id in (select manager from employees)

Or

Select e1.name from employees e1 inner join employees e2 ON e1.id = e2.manager

Database Interview Question-14. How to get name of database?

Answer: select db_name();

Database Interview Question-15. How to get database version?

Answer: select @@version

Database Interview Question-16. If table is truncated, can it be roll backed?

Answer: No

Database Interview Question-17. What is clustered index? How many Clustered indexes can you have on a table.

Answer: A clustered index physically sorts the records on the disk based on the index. Hence only one clustered index per table is feasible

Database Interview Question-18. What is “MINUS” used for?

Answer:  MINUS returns only those results from first result set which are not present in second result set

Database Interview Question-19. Write a query to get all the employees who are managers

Answer: select distinct e.NAME as Employee, m.NAME as Manager from EMPLOYEE e inner join EMPLOYEE m on e.ID = m.MANAGER;

Database Interview Question-20. Write a query to get all the employees who do not have managers

Answer: Select ID, NAME from employee where MANAGER  is NULL;

Database Interview Question-21.  Suppose a table X has 3 duplicate rows and you want to delete 2 redundant rows

| ID | Name | Level |
| 101 | Jack | 3 |
| 101 | Jack | 3 |
| 101 | Jack | 3 |

Answer: BEGIN; set rowcount 2; delete from X; END;

Database Interview Question-22. There is a table “Employee” having two columns – Emp_Name and Office_Locations. Write a query that will display all office locations having more than 100 employees.

Answer: select Office_Locations from (select Office_Locations,  COUNT(Emp_name) as count1 from employee_table GROUP BY  Office_Locations) HAVING count1>=100;

Database Interview Question-23. Can a table span multiple partitions?

Answer: Yes

Database Interview Question-24. What is foreign key?

Answer: Foreign key is a column or a combination of columns that is used to establish and enforce a link between two table

Database Interview Question-25. How to remove duplicates from a table?

SELECT DISTINCT * INTO NODUPLICATES FROM DUPLICATES;

DROP TABLE DUPLICATES;

RENAME TABLE NODUPLICATES TO DUPLICATES

Database Interview Question-26. How do you measure performance of a stored proc?

Answer: There are three ways to measure performance of stored procedure.

First way:

DECLARE @start datetime, @stop datetime

SET @start = GETDATE()

EXEC mystoredprocedure

SET @stop = GETDATE()

Second way:

SET STATISTICS TIME ON

EXEC mystoredprocedure

Third way:

SET STATISTICS IO ON

EXEC mystoredprocedure

Database Interview Question-27. How do you define constraints?

Answer: CREATE TABLE myTable

(

column_name1 data_type(size) constraint_name,

column_name2 data_type(size) constraint_name,

column_name3 data_type(size) constraint_name,

....

);

As example, we have “NOT NULL” and “primary key” constraints in below table

CREATE TABLE Persons

(

ID int NOT NULL,

LastName varchar(255) NOT NULL,

FirstName varchar(255),

Address varchar(255),

City varchar(255),

CONSTRAINT pk_ID PRIMARY KEY (ID)

)

Database Interview Question-28. What all constraints are supported by MYSQL?

Answer: We have the following constraints:

A. NOT NULL – The constraint ensures that a column cannot store NULL value

B. UNIQUE - The constraint ensures that column cannot have duplicate value

C. PRIMARY KEY – This constraint is combination of UNIQUE and NOT NULL

D. FOREIGN KEY – This constraint ensures that referential integrity among multiple table is maintained

E. CHECK - This constraint ensures that the value in a column meets a specific condition

F. DEFAULT - This constraint specifies a default value for a column

Database Interview Question-29. What are the differences between WHERE clause and HAVING clause?

Answer: WHERE clause cannot be used with aggregates, but the HAVING clause can be used.

WHERE is less expensive than that of HAVING

Database Interview Question-30. Write a simple Stored Procedure.

Answer: Here is a sample stored procedure

CREATE PROCEDURE GetEmployeenameEmailInOutputVariable

(

@ID INT,                   --Input parameter

@NAME VARCHAR (200) OUT,    -- Output parameter to collect name

@EMAIL VARCHAR (200)OUT     -- Output Parameter to collectemail

)

AS

BEGIN

SELECT @NAME= Firstname+' '+Lastname,

    @EMAIL=EMAIL FROM EMPLOYEE WHERE ID=@ID

END

Database Interview Question-31. What are the disadvantages of normalization?

Answer: More one normalizes database, more tables, more joins are required and takes lot of time to retrieve required records

Database Interview Question-32. Write SQL query to fetch all bank account details whose name starts with “Shyam”

Answer: Select * from account where name LIKE ‘%Shyam%’;

Database Interview Question-33. Write SQL query to fetch top 3 accounts having highest balance

Answer: SYBASE: select top 3 * from account order by balance desc;

MYSQL: select * from employee order by salary desc limit 1,3

Oracle: select * from employee order by salary where rownum < 3

Database Interview Question-34. Write SQL query to fetch bottom 3 accounts having  lowest balance

Answer:  SYBASE: select top 3 * from account order by balance asc;

MYSQL: select * from employee order by salary asc limit 1,3

Oracle: select * from account order by balance asc where rownum<3;

Database Interview Question-35. Write SQL query to update balance of all account with 6% interest

Answer: UPDATE account SET BALANCE = BALANCE * 1.06;

Database Interview Question-36. Write SQL query to find out total balances maintained in whole bank

Answer: SELECT SUM(balance) AS total FROM account;

Database Interview Question-37. Write SQL query to find out number of customers having balance 100000.

Answer: SELECT COUNT(balance) AS "Number of customers" FROM account WHERE balance = 100000;

Database Interview Question-38. Write a SQL query to return first 100 account records.

Answer: select top 100 * from account;

Database Interview Question-39. Write SQL query to return count of customers having  balance between 100000 to 200000 group by balance

Answer: select balance, COUNT(*) from account where balance > 100000 AND balance < 200000  GROUP BY balance

Database Interview Question-40. In SQL which runs faster “sub queries” or join?

Answer: Join

Database Interview Question-41. Which of the following SQL clauses is used to sort a result set?

1.  SORT

2.  ORDER BY

3.  ARRANGE

4.  SORTED BY

Answer: B

Database Interview Question-42. The FROM SQL keyword is used to

A.  Specify the table we are modifying.

B.  Specify the table we are inserting data in.

C.  Specify the table we are selecting or deleting from.

Answer: C

Database Interview Question-43. What does ACID stand for?

A.  Access. Constraint. Index. Data.

B.  Atomicity. Consistency. Isolation. Durability.

C. Access. Consistency. Isolation. Data.

Answer: B

Database Interview Question-44. Which of the following SQL statements deletes all rows in table called SalesData?

A.  DELETE * FROM SalesData

B.  DELETE FROM SalesData

C. DELETE SalesData

D.  DELETE ALL SalesData  

Answer: B

Database Interview Question-45. Which of the following SQL clauses is used to select data from 2 or more tables?

A.  HAVING

B.  WHERE

C.  JOIN   

Answer: JOIN

Database Interview Question-46. The INNER JOIN clause…

A.  returns all rows that have matching value in the field on which the 2 tables are joined.

B.  returns all rows from 2 tables.

C.  returns only the rows from the first table, which have non-matching values with the second table in the field on which the 2 tables are joined.

Answer: A

Database Interview Question-47. The TRUNCATE TABLE…

A.  checks if the table has primary key specified

B.  deletes all rows from a table

C.  deletes the table

Answer: B

Database Interview Question-48. The table columns are also known as

1.  Attributes

2.  Fields

3.  Records

Answer: B

Database Interview Question-49. The UNION SQL clause can be used with…

1.  the SELECT clause only

2.  the UPDATE clause only

3.  the DELETE and UPDATE clauses

4.  none of the other three

Answer: A

Database Interview Question-50. The HAVING clause can be used only with

1.  JOIN clause.

2.  INSERT clause

3.  SELECT clause

4.  DELETE clause.

Answer: C

Database Interview Question-51. Which SQL keyword is used to retrieve only unique values?

1.  DISTINCT

2.  DISTINCTIVE

3.  DIFFERENT

4.  UNIQUE

Answer: A

Database Interview Question-52. Which of the following is true?

1.  TRUNCATE TABLE has to be used along with a WHERE clause

2.  TRUNCATE TABLE deletes table from a database

3.  TRUNCATE TABLE is identical to DELETE statement without WHERE clause and both remove all rows in a table.

Answer: C

Database Interview Question-53. What does the FROM SQL keyword specify?

1.  The FROM SQL keyword specifies the tables, views, and joined tables used in SELECT, UPDATE and DELETE SQL statements.

2.  The FROM SQL keyword specifies a search condition.

3.  The FROM SQL keyword specifies a column list.

Answer: A

Database Interview Question-54. What is the purpose of the SQL AS clause?

1.  The AS SQL clause is used change the name of a column in the result set or to assign a name to a derived column.
2.  The AS clause defines a search condition.
3.  The AS clause is used with the JOIN clause only.

Answer: A

Database Interview Question-55. What does the UNION operator do?

1.  The UNION operator sorts the selected result set.

2.  The UNION operator combines the results of two or more queries into a one result that includes all the rows from the queries in the union.

3.  The UNION operator behaves the same as the JOIN SQL clause.

Answer: B

Database Interview Question-56. The UPDATE SQL clause can…

1.  update only one row at a time.

2.  update more than one row at a time.

3.  delete only one row at a time.

4.  delete more than one row at a time.

Answer: B

Database Interview Question-57. What all can be optimized in Database

Answer: Following parameters can be optimized

1.  Memory

· Database buffer cache

· Redo log buffer

· Shared pool

· Large pool

2.  Disk I/O: Database files needs to be properly sized and placed to provide maximum disk subsystem throughput
3.  Database Contention: Check whether database locks, latches and wait events can be removed/moved
4.  Operating System: Monitor and tune operating system CPU, I/O and memory utilization

Database Interview Question-58. What is the command to check database statistics?

Answer: SHOW STATISTICS

Database Interview Question-59. How to set storage engine for a table

Answer: SET storage_engine=MYISAM; or

CREATE TABLE test (id INTEGER) ENGINE = MYISAM;  

Database Interview Question-60. Did you perform any database optimization tasks?

Answer: Yes, please explain with example, like you created a new index or added index in an existing query to reduce “query execution” time, if you are working in database, you must be able to come up with a real life example from your database project

Database Interview Question-61. How to find out server name

Answer: select @@servername

Database Interview Question-62. Can primary key be null?

Answer: No

Database Interview Question-63. Create an employee table with ID, Name  and Salary, insert 10 records into the employee table

Answer: create table TEST(employeeid INTEGER, employeename VARCHAR(20), employeesalary INTEGER);

insert into TEST values(1,'A',1000);

insert into TEST values(2,'B', 1000);

insert into TEST values(3,'C', 1000);

insert into TEST values(4,'D', 1000);

insert into TEST values(5,'E', 1000);

insert into TEST values(6,'F', 1000);

insert into TEST values(7,'G', 1000);

insert into TEST values(8,'H', 1000);

insert into TEST values(9,'I', 1000);

insert into TEST values(10,'J',4);

Database Interview Question-64. Explain constraint with example

Answer: Create table EMPLOYEE(

ID INTEGER,

NAME STRING,

SALARY INTEGER        not null   constraint check_salary  SALARY ( > 0) and (SALARY < 1000))

Answer: Query plan is collection of steps required to fetch records corresponding to the query

Below set of questions are left as an exercise for the reader.

Write SQL query to create following tables

Employee (ID, NAME, LOCATION, DEPARTMENT, BANKACCOUNTID, SEX)

Bank Account (BANKACCOUNTID, OPENINGDATE, BALANCE)

Insert 5 employee (male and female) details for each of 5 departments (e.g. Finance, IT, Admin, Facility, Legal) and corresponding bank account details.

Database Interview Question-65. Write SQL query to retrieve all employees having bank balance more than 10000.

Database Interview Question-66. Write SQL query to increase balance of all female employees by 5000.

Database Interview Question-67. Write SQL query to find out count of all male employees having balance between 5000 to 1000

Database Interview Question-68. Increase balance of each of the above employees by 1000

Database Interview Question-69. Write SQL query to find the total balance of all employees working in finance department

Database Interview Question-70. Write SQL query to find department wise average balance for employee.

# Conclusion

Hope this database interview questions and answers book makes you better prepared for next interview. Please devote some time to write new database queries/stored procedures on a daily basis. This will help you to keep up to date with latest database technology developments.

# About Author

Chinmoy is an author, innovator, entrepreneur and solution architect. He has written dozen books on "software technology", "social science" and "adult coloring". He loves mentoring people. Please feel free to contact him at [http://www.linkedin.com/in/chinmoym](http://www.linkedin.com/in/chinmoym)