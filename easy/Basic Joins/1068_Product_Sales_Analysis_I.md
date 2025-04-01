# 1068. Product Sales Analysis I

#### [Link] 
https://leetcode.com/problems/product-sales-analysis-i/submissions/1592622941

#### [Question]
Report the product_name, year, and price for each sale_id in the Sales table.

Return the resulting table in any order.


#### [Input]
Sales table:
+---------+------------+------+----------+-------+
| sale_id | product_id | year | quantity | price |
+---------+------------+------+----------+-------+ 
| 1       | 100        | 2008 | 10       | 5000  |
| 2       | 100        | 2009 | 12       | 5000  |
| 7       | 200        | 2011 | 15       | 9000  |
+---------+------------+------+----------+-------+
Product table:
+------------+--------------+
| product_id | product_name |
+------------+--------------+
| 100        | Nokia        |
| 200        | Apple        |
| 300        | Samsung      |
+------------+--------------+

#### [Output]
+--------------+-------+-------+
| product_name | year  | price |
+--------------+-------+-------+
| Nokia        | 2008  | 5000  |
| Nokia        | 2009  | 5000  |
| Apple        | 2011  | 9000  |
+--------------+-------+-------+

#### [Solution]
SELECT p.product_name, s.year, s.price
FROM Sales s
JOIN Product p
USING(product_id)
