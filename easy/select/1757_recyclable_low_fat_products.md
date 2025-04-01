# 1757. Recyclable and Low Fat Products

#### [Link] 
https://leetcode.com/problems/recyclable-and-low-fat-products/submissions/1592591638

#### [Question]
Find the ids of products that are both low fat and recyclable.
Return the result table in any order.


#### [Input]
Products table:
+-------------+----------+------------+
| product_id  | low_fats | recyclable |
+-------------+----------+------------+
| 0           | Y        | N          |
| 1           | Y        | Y          |
| 2           | N        | Y          |
| 3           | Y        | Y          |
| 4           | N        | N          |
+-------------+----------+------------+

#### [Output]
+-------------+
| product_id  |
+-------------+
| 1           |
| 3           |
+-------------+

#### [Solution]
SELECT product_id
FROM Products
WHERE (low_fats = 'Y') AND (recyclable = 'Y')
