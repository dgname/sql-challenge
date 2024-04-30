### Employee Management System Data Analysis

#### Overview
This repository contains SQL scripts for creating and analyzing tables related to an employee management system. The provided SQL scripts create tables for employees, departments, titles, salaries, department employees, and department managers. Additionally, the repository includes SQL queries to perform various analyses on the data.

## Table Creation
The following tables are created:
- `titles`: Contains information about job titles.
- `departments`: Contains information about departments.
- `employees`: Contains information about employees, including their personal details and job title.
- `salaries`: Contains information about employee salaries.
- `dept_emp`: Represents the relationship between employees and departments.
- `dept_manager`: Represents the relationship between managers and departments.

#### Relationships and Key Constraints
- **`titles` Table**:
  - Primary Key: `title_id`
- **`departments` Table**:
  - Primary Key: `dept_no`
- **`employees` Table**:
  - Primary Key: `emp_no`
  - Foreign Key: `emp_title_id` references `titles(title_id)`
- **`salaries` Table**:
  - Primary Key: `emp_no`
  - Foreign Key: `emp_no` references `employees(emp_no)`
- **`dept_emp` Table**:
  - Composite Primary Key: `(emp_no, dept_no)`
  - Foreign Key: `emp_no` references `employees(emp_no)`
  - Foreign Key: `dept_no` references `departments(dept_no)`
- **`dept_manager` Table**:
  - Primary Key: `emp_no`
  - Foreign Key: `dept_no` references `departments(dept_no)`
  - Foreign Key: `emp_no` references `employees(emp_no)`

Many employees can work in a department, but each employee can only belong to one department at a time.

One department can have multiple managers, but each manager is assigned to only one department at a time.

Only one employee can be the manager of a department.

Each employee has only one corresponding salary.

Many employees can have the same job title.

## Data Analysis
The provided SQL queries perform the following analyses:
1. List the employee number, last name, first name, sex, and salary of each employee.
2. List the first name, last name, and hire date for the employees who were hired in 1986.
3. List the manager of each department along with their department number, department name, employee number, last name, and first name.
4. List the department number for each employee along with that employee’s employee number, last name, first name, and department name.
5. List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B.
6. List each employee in the Sales department, including their employee number, last name, and first name.
7. List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name.
8. List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name).

#### Usage
1. Execute the SQL scripts to create the necessary tables.
2. Run the provided SQL queries to perform the desired analyses on the data.

#### Requirements
- A database management system that supports SQL (e.g., MySQL, PostgreSQL).

Readme partially created with ChatGPT's help.
