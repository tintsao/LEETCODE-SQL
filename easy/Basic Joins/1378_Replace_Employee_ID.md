# 1378. Replace Employee ID With The Unique Identifier

#### [Link] 
https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/submissions/1592621811

#### [Question]
Show the unique ID of each user, If a user does not have a unique ID replace just show null.

Return the result table in any order.


#### [Input]
Employees table:
+----+----------+
| id | name     |
+----+----------+
| 1  | Alice    |
| 7  | Bob      |
| 11 | Meir     |
| 90 | Winston  |
| 3  | Jonathan |
+----+----------+
EmployeeUNI table:
+----+-----------+
| id | unique_id |
+----+-----------+
| 3  | 1         |
| 11 | 2         |
| 90 | 3         |
+----+-----------+

#### [Output]
+-----------+----------+
| unique_id | name     |
+-----------+----------+
| null      | Alice    |
| null      | Bob      |
| 2         | Meir     |
| 3         | Winston  |
| 1         | Jonathan |
+-----------+----------+

#### [Solution]
SELECT e2.unique_id, e1.name
FROM Employees e1
LEFT JOIN EmployeeUNI e2
USING (id)
