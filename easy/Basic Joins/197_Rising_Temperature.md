# 197. Rising Temperature

#### [Link] 
https://leetcode.com/problems/rising-temperature/submissions/1592659817

#### [Question]
Find all dates' id with higher temperatures compared to its previous dates (yesterday).

Return the result table in any order.


#### [Input]
Weather table:
+----+------------+-------------+
| id | recordDate | temperature |
+----+------------+-------------+
| 1  | 2015-01-01 | 10          |
| 2  | 2015-01-02 | 25          |
| 3  | 2015-01-03 | 20          |
| 4  | 2015-01-04 | 30          |
+----+------------+-------------+

#### [Output]
+----+
| id |
+----+
| 2  |
| 4  |
+----+

#### [Solution]
SELECT product_id
FROM Products
WHERE (low_fats = 'Y') AND (recyclable = 'Y')
SELECT id 
FROM (
    SELECT 
    id, 
    recordDate,
    temperature, 
    LAG(temperature, 1) OVER(ORDER BY recordDate) AS last_temp, 
    LAG(recordDate) OVER(ORDER BY recordDate) AS last_date
    FROM Weather
) AS wsub
WHERE (temperature > last_temp) AND DATEDIFF(recordDate, last_date) = 1
