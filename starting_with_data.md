Question 1: Find all duplicate records

SQL Queries:
SELECT "fullVisitorId", COUNT("fullVisitorId")
FROM all_sessions
GROUP BY "fullVisitorId"
HAVING COUNT("fullVisitorId") > 1

OR

SELECT
    "fullVisitorId",
    COUNT( "fullVisitorId" )
FROM
    all_sessions
GROUP BY
    "fullVisitorId"
HAVING
    COUNT( "fullVisitorId" )> 1
ORDER BY
    "fullVisitorId";

### Remove NULL columns which do not bring any value to the data
ALTER table all_sessions
        DROP COLUMN searchkeyword, product_refund_amount,
        item_quality, item_revenue

Answer: The data is nice and clean

Thanks to the above query I found the number of dublicates in "fullvisitorId". Looks like most of the "fullvisitorId" are repeated at least twice.


Question 2: Find the total number of unique visitors (`fullVisitorID`)

SQL Queries:
SELECT COUNT( DISTINCT "fullVisitorId" ) as "fullVisitorIds"
FROM all_sessions;

Answer: 14223


Question 3: Find the total number of unique visitors by referring sites

SQL Queries:
SELECT city, COUNT( DISTINCT "fullVisitorId" ) as "fullVisitorIds"
FROM all_sessions
group by city;

Answer: Unique visitors with no cities: 329, the rest has different number of cities associated with the unique "fullVisitorId"


Question 4: Find each unique product viewed by each visitor

SQL Queries (number of unique products):

SELECT COUNT ( DISTINCT "v2ProductName" ) as "v2ProductName"
FROM all_sessions;

Answer: 471 unique Products


