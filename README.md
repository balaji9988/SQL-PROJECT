# SQLtech Employee Database Analysis

## Project Overview
SQLtech is a startup specializing in Data Science, working on various projects such as fraud detection, self-driving cars, supply chain optimization, and more. This project focuses on analyzing employee data to generate reports required by the HR department for performance reviews and project evaluations.

## Technologies Used
- **SQL (Structured Query Language)**
- **MySQL** - Open-source relational database management system

## Dataset
The project involves three datasets:
1. **data_science_team.csv** - Information about the data science team
2. **proj_table.csv** - Details of projects employees are working on
3. **emp_record_table.csv** - Employee details, including their department, experience, and ratings

## SQL Queries & Objectives

1. **Database Creation & Data Import**
   - Create an `employee` database
   - Import datasets into MySQL tables
   ```sql
   CREATE DATABASE employee;
   USE employee;
   LOAD DATA INFILE 'data_science_team.csv' INTO TABLE emp_record_table;
   LOAD DATA INFILE 'proj_table.csv' INTO TABLE proj_table;
   LOAD DATA INFILE 'emp_record_table.csv' INTO TABLE emp_record_table;
   ```

2. **Employee Details Retrieval**
   - Fetching EMP_ID, FIRST_NAME, LAST_NAME, GENDER, and DEPARTMENT
   ```sql
   SELECT EMP_ID, FIRST_NAME, LAST_NAME, GENDER, DEPARTMENT FROM emp_record_table;
   ```

3. **Filtering Employee Ratings**
   - Employees with ratings less than 2, greater than 4, and between 2 and 4
   ```sql
   SELECT EMP_ID, FIRST_NAME, LAST_NAME, GENDER, DEPARTMENT, EMP_RATING FROM emp_record_table WHERE EMP_RATING < 2;
   ```

4. **Concatenation of Names in Finance Department**
   ```sql
   SELECT CONCAT(FIRST_NAME, ' ', LAST_NAME) AS NAME FROM emp_record_table WHERE DEPARTMENT = 'Finance';
   ```

5. **Employee List from Multiple Departments using UNION**
   ```sql
   SELECT * FROM emp_record_table WHERE DEPARTMENT = 'Healthcare' UNION ALL SELECT * FROM emp_record_table WHERE DEPARTMENT = 'Finance';
   ```

6. **Min and Max Salary by Role**
   ```sql
   SELECT ROLE, MIN(SALARY) AS Min_Salary, MAX(SALARY) AS Max_Salary FROM emp_record_table GROUP BY ROLE;
   ```

7. **Employee Ranking Based on Experience**
   ```sql
   DELIMITER //
   CREATE PROCEDURE exp_emp() BEGIN SELECT * FROM emp_record_table WHERE EXP > 3; END //
   CALL exp_emp;
   ```

8. **View for High Salary Employees**
   ```sql
   CREATE VIEW HighSalaryEmp AS SELECT EMP_ID, FIRST_NAME, GENDER, EXP, COUNTRY, TOTAL_SALARY FROM emp_record_table WHERE TOTAL_SALARY > 6000;
   ```

9. **Nested Query for Employees with More than 10 Years Experience**
   ```sql
   CREATE VIEW MoreThanTen AS SELECT EMP_ID, FIRST_NAME, GENDER, EXP FROM emp_record_table WHERE EXP > 10;
   ```

10. **Stored Procedure for Employees with More than 3 Years Experience**
   ```sql
   CREATE PROCEDURE emp_count1(INOUT records INT, IN exp INT) BEGIN SELECT COUNT(*) INTO records FROM emp_record_table WHERE EXP = exp; END;
   ```

11. **Bonus Calculation**
   ```sql
   SELECT EMP_ID, FIRST_NAME, LAST_NAME, ROLE, DEPARTMENT, SALARY, EMP_RATING, (0.05 * SALARY * EMP_RATING) AS BONUS FROM emp_record_table;
   ```

12. **Average Salary Distribution by Continent & Country**
   ```sql
   SELECT CONTINENT, COUNTRY, AVG(SALARY) AS Average FROM emp_record_table GROUP BY CONTINENT, COUNTRY;
   ```

## How to Run the Project
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/SQLtech-Employee-Analysis.git
   ```
2. Import the dataset into MySQL
3. Run the SQL queries provided in `queries.sql`
4. Analyze the generated reports

## Author
**K Balaji** - Under the guidance of Mr. Veera (Besant Technologies)

## License
This project is open-source and available for educational purposes.

