           SQL project🎗️
Project Title:
 SQLtech is a startup that works in the Data Science field

Description
 SQLtech is a startup that works in the Data Science field.
SQLtech has worked on fraud detection, market basket, self-driving cars,
supply chain, algorithmic early detection of lung cancer, customer
sentiment, and the drug discovery field. With the annual appraisal cycle
around the corner, the HR department has asked you (Junior Database
Administrator) to generate reports on employee details, their performance,
and on the project that the employees have undertaken, to analyze the
employee database and extract specific data based on different
requirements.

1 Create a database named employee, then import data_science_team.csv
proj_table.csv and emp_record_table.csv into the employee database from the given
resources.

 data_science_team
query
 use tamil;
 select * from emp_record_table;
 
 2 Write a query to fetch EMP_ID, FIRST_NAME, LAST_NAME, GENDER, and
DEPARTMENT from the employee record table, and make a list of employees and
details of their department.

 Query
 use tamil;
 create table notnull21
 (emp_id int not null,First_Name VARCHAR(35),
Last_Name VARCHAR(20),GENDER varchar(45),DEPARTMENT varchar(55));
select * from notnull21;
insert into notnull21(emp_ID, FIRST_NAME, LAST_NAME,Gender,Department)
values(45, "kondamari","balaji","m","mech"),
(20, "john","anil","m","ece"),
(30, "kondamari","harish","m","it");
select * from notnull21;

3. Write a query to fetch EMP_ID, FIRST_NAME, LAST_NAME, GENDER,
DEPARTMENT, and EMP_RATING if the EMP_RATING is:
 less than two
 greater than four
 between two and four
less than two

Query
 SELECT EMP_ID, FIRST_NAME, LAST_NAME, GENDER, DEPt, EMP_RATING
 FROM emp_record_table
 WHERE EMP_RATING < 2;
greater than four

Query
 SELECT EMP_ID, FIRST_NAME, LAST_NAME, GENDER, DEPt, EMP_RATING
FROM emp_record_table
WHERE EMP_RATING > 4;

