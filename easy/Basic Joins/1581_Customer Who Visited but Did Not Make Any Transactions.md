# 1581. Customer Who Visited but Did Not Make Any Transactions

#### [Link] 
https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/submissions/1592651144

#### [Question]
Find the IDs of the users who visited without making any transactions and the number of times they made these types of visits.

Return the result table sorted in any order.

#### [Input]
Visits
+----------+-------------+
| visit_id | customer_id |
+----------+-------------+
| 1        | 23          |
| 2        | 9           |
| 4        | 30          |
| 5        | 54          |
| 6        | 96          |
| 7        | 54          |
| 8        | 54          |
+----------+-------------+
Transactions
+----------------+----------+--------+
| transaction_id | visit_id | amount |
+----------------+----------+--------+
| 2              | 5        | 310    |
| 3              | 5        | 300    |
| 9              | 5        | 200    |
| 12             | 1        | 910    |
| 13             | 2        | 970    |
+----------------+----------+--------+

#### [Output]
+-------------+----------------+
| customer_id | count_no_trans |
+-------------+----------------+
| 54          | 2              |
| 30          | 1              |
| 96          | 1              |
+-------------+----------------+

#### [Solution]
SELECT customer_id, COUNT(*) AS count_no_trans
FROM Visits
WHERE visit_id NOT IN (
    SELECT DISTINCT visit_id 
    FROM Transactions
)
GROUP BY customer_id
