# 584. Find Customer Referee

#### [Link] 
https://leetcode.com/problems/find-customer-referee/submissions/1592607981

#### [Question]
Find the names of the customer that are not referred by the customer with id = 2.
Return the result table in any order.


#### [Input]
Customer table:
+----+------+------------+
| id | name | referee_id |
+----+------+------------+
| 1  | Will | null       |
| 2  | Jane | null       |
| 3  | Alex | 2          |
| 4  | Bill | null       |
| 5  | Zack | 1          |
| 6  | Mark | 2          |
+----+------+------------+

#### [Output]
+------+
| name |
+------+
| Will |
| Jane |
| Bill |
| Zack |
+------+

#### [Solution]
SELECT name
FROM Customer
WHERE (referee_id != 2) OR (referee_id IS NULL)
