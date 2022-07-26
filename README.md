# Query-Script-Examples
SQL Code Examples

#Write an SQL query to calculate the bonus of each employee. 
#The bonus of an employee is 100% of their salary if the ID of the employee is an odd number and the employee name does not start with the character 'M'. 
#The bonus of an employee is 0 otherwise.
#Return the result table ordered by employee_id.

SELECT employee_id,
CASE WHEN
employee_id % 2 <> 0 AND name NOT LIKE 'M%' THEN salary ELSE 0
END AS bonus
FROM Employees
ORDER BY employee_id

#Write an SQL query to swap all 'f' and 'm' values (i.e., change all 'f' values to 'm' and vice versa) with a single update statement and no intermediate temporary tables.

UPDATE salary SET sex =
CASE WHEN sex ='f' THEN 'm'
    WHEN sex = 'm' THEN 'f'
    END
    
#Write an SQL query to delete all the duplicate emails, keeping only one unique email with the smallest id.

DELETE table1
FROM person AS table1
JOIN person AS table2
ON table1.email = table2.email
WHERE table1.id > table2.id
