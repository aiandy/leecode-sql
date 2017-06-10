# 175.combine 2 tables
#Write a SQL query for a report that provides the following information 
#for each person in the Person table, regardless if there is an address for each of those people:

SELECT FirstName,
        LastName,
        City,       
        State
FROM Person LEFT JOIN Address
    ON Person.PersonId=Address.PersonId
		
#176.Select the second highest salary
SELECT max(Salary) AS SecondHighestSalary FROM Employee
    WHERE Salary<(SELECT MAX(Salary) FROM Employee)
LIMIT 1
#max() will return into NULL if the value does not exist.
