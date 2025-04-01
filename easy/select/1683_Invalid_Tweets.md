# 1683. Invalid Tweets

#### [Link] 
https://leetcode.com/problems/invalid-tweets/submissions/1592616144

#### [Question]
Find the IDs of the invalid tweets. The tweet is invalid if the number of characters used in the content of the tweet is strictly greater than 15.

Return the result table in any order.

#### [Input]
Tweets table:
+----------+-----------------------------------+
| tweet_id | content                           |
+----------+-----------------------------------+
| 1        | Let us Code                       |
| 2        | More than fifteen chars are here! |
+----------+-----------------------------------+

#### [Output]
+----------+
| tweet_id |
+----------+
| 2        |
+----------+

#### [Solution]
SELECT tweet_id 
FROM Tweets
WHERE LENGTH(content) > 15
