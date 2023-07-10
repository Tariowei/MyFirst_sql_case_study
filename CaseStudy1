## 1. Select employees first name, last name, job_id and salary whose first name starts with alphabet S
SELECT first_name, last_name, job_id, salary
 FROM employees
 WHERE first_name LIKE ("s%");
 
## 2. Write a query to select employee with the highest salary
SELECT first_name, last_name, job_id, salary
 FROM employees
 ORDER BY salary DESC
 LIMIT 1;
 
## 3. Select employee with the second highest salary
SELECT first_name, last_name, job_id, salary
 FROM employees
 ORDER BY salary DESC
 LIMIT 1,1;
 
## 4. Fetch employees with 2nd or 3rd highest salary
SELECT first_name, last_name, job_id, salary
 FROM employees
 ORDER BY salary DESC
 LIMIT 2,1;
 
## 5. Write a query to select employees and their corresponding managers and their salaries
SELECT employee.first_name, employee.last_name,
		manager.first_name AS mgr_first_name,
        manager.last_name AS mgr_last_name,
        manager.salary AS mgr_salary
FROM employees employee, employees manager
WHERE employee.employee_id = manager.manager_id;

## 6. Write a query to show count of employees under each manager in descending order
SELECT employee.first_name AS mgr_first_name, manager.manager_id,
        COUNT(manager.manager_id) AS num_of_subordinate
FROM employees employee, employees manager
WHERE employee.employee_id = manager.manager_id
GROUP BY manager.manager_id
ORDER BY COUNT(manager.manager_id) DESC;

## 7. Find the count of employees in each department
SELECT employees.department_id, departments.department_name,
COUNT(employees.department_id) AS num_of_employees
FROM employees, departments
WHERE employees.department_id = departments.department_id
GROUP BY departments.department_id
ORDER BY COUNT(employees.department_id) DESC;

## 8. Get the count of employees hired year wise
SELECT YEAR(hire_date) AS hire_date,
 COUNT(employee_id) AS num_of_employees_hired
FROM employees
GROUP BY YEAR(hire_date) 
ORDER BY YEAR(hire_date) ASC;

## 9. Find the salary range of employees
SELECT MIN(salary) AS min_salary, MAX(salary) AS max_salary
FROM employees;

## 10. Write a query to divide people into three groups based on their salaries
SELECT CASE
		WHEN salary <= 5000 THEN "group_1: under 5000"
        WHEN salary > 5000 AND salary <= 10000 THEN "group_2: 5000 to 10000"
        ELSE "group 3: over 10000"
	END AS salary_group,
    COUNT(*) AS group_count
    FROM employees
    GROUP BY salary_group
      ORDER BY COUNT(*) DESC;

## 11. Select the employees whose first_name contains “an”
SELECT first_name
FROM employees
WHERE first_name LIKE("%an%");

## 12. Select employee first name and the corresponding phone number in the format (_ _ _)-(_ _ _)-(_ _ _ _)
SELECT first_name, phone_number
FROM employees;

## 13. Find the employees who joined in August, 1994.
SELECT employee_id, first_name, YEAR(hire_date) AS year_hired, 
		MONTH(hire_date) AS month_hired
FROM employees
WHERE YEAR(hire_date) = 1994 AND MONTH(hire_date) = 8;

## 14. Write an SQL query to display employees who earn more than the average salary in that company
SELECT employee_id, first_name, last_name, salary
FROM employees
WHERE salary > (SELECT AVG(salary)
FROM employees)
ORDER BY salary DESC;

## 15. Find the maximum salary from each department.
SELECT departments.department_name, MAX(employees.salary) AS maximum_salary
FROM departments,employees
WHERE departments.department_id = employees.department_id 
GROUP BY departments.department_id;

## 16. Write a SQL query to display the 5 least earning employees
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary ASC
LIMIT 5;

## 17. Find the employees hired in the 80s
SELECT first_name, last_name, hire_date
FROM employees
WHERE YEAR(hire_date) BETWEEN 1980 AND 1989;

## 18. Display the employees first name and the name in reverse order
SELECT first_name, REVERSE(first_name) AS reversed_name
FROM employees;

## 19. Find the employees who joined the company after 15th of the month
SELECT first_name, last_name, hire_date
FROM employees
WHERE DAY(hire_date) BETWEEN 16 AND 31;

## 20. Display the managers and the reporting employees who work in different departments
SELECT employee.employee_id, employee.first_name, employee.department_id,
 manager.employee_id AS manager_id,manager.first_name AS manager_first_name,
 manager.department_id AS manager_dept_id
FROM employees employee, employees manager
WHERE employee.manager_id = manager.employee_id
AND employee.department_id != manager.department_id;
