Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
1.
   SELECT "country", "city", SUM(CAST("totalTransactionRevenue"/1000000 as real)) as total_transaction_revenue
from all_sessions
WHERE "totalTransactionRevenue" IS NOT NULL
AND city != 'not available in data demo dataset'
GROUP by country, city
ORDER by total_transaction_revenue DESC

Answer: "United States"	"not available in demo dataset"	6092.561
"United States"	"San Francisco"	1564.32
"United States"	"Sunnyvale"	992.23
"United States"	"Atlanta"	854.44
"United States"	"Palo Alto"	608
"Israel"	"Tel Aviv-Yafo"	602
"United States"	"New York"	530.36
"United States"	"Mountain View"	483.36
"United States"	"Los Angeles"	479.48
"United States"	"Chicago"	449.52002
"Australia"	"Sydney"	358
"United States"	"Seattle"	358
"United States"	"San Jose"	262.38
"United States"	"Austin"	157.78
"United States"	"Nashville"	157
"United States"	"San Bruno"	103.77
"Canada"	"Toronto"	82.16
"Canada"	"New York"	67.99
"United States"	"Houston"	38.98
"United States"	"Columbus"	21.99
"Switzerland"	"Zurich"	16.99

**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
City, Country:

select AVG(distinct "productRevenue"), "country", "city"
from all_sessions
group by "productRevenue", country, city;


Answer:
58656666.000000000000	"United States"	
60365000.000000000000	"United States"	
120000000.000000000000	"United States"	"Sunnyvale"
176400000.000000000000	"United States"	


**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
    SELECT country, city, v2productcategory, date, COUNT(v2_productcategory) FROM(
SELECT country, city, DATE_PART('year', TO_DATE(date, 'YYYYMMDD')) as date, split_part(v2productcategory, '/', -2) AS v2productcategory
FROM all_sessions) as sub
	WHERE city != 'not in demo dataset' AND city !='(not set)'
	GROUP BY 1,2,3
	ORDER BY count DESC


Question 5:  How much time did the average person spent on the website by country in seconds?

SELECT country, AVG("timeonsite") as avgtime
FROM all_sessions
GROUP by country
HAVING AVG("timeonsite") is not NULL
ORDER by avgtime DESC

Answer: Peru: 859.181818181818
        Nigeria: 752.500000000
        Tunisia: 726.000000000
        Slovenia: 969.00000000
        Kenya: 572.33333333333 and etc






>>>>>> IMPORTANT NOTE: the above data shows Q5 and Q2:
Countries where people spend more time browsing website, buy less products. The top buyer is USA but in regards of the time spent browsing website they are not in first 5. Its important for the decision making, marketing campaigns and resources allocation. Byers in USA tend to spend minimum time selecting the products, more tend to buy thinhs faster than other countries. Could be due to economic differences. 


