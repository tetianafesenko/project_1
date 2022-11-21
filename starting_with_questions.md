Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
1.
    select "city", "country", "transactions"
from all_sessions

2.
select "city", "country", MAX(distinct "transactions")
from all_sessions
group by transactions, city, country;


Answer: 21



**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
City, Country:

select AVG(distinct "productRevenue"), "country", "city"
from all_sessions
group by "productRevenue", country, city;


Answer:
58656666.000000000000	"United States"	"not available in demo dataset"
60365000.000000000000	"United States"	"not available in demo dataset"
120000000.000000000000	"United States"	"Sunnyvale"
176400000.000000000000	"United States"	"not available in demo dataset"



**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
    select "country", "city", "v2ProductName"
from all_sessions



Answer:





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:







