What issues will you address by cleaning the data?

Data cleaning is very important step in analyzing, preparing and using the data. Cleaning the data helps to remove any dublicates, corrupted data, missing information or incomplete information within the dataset. Imputing the raw data is the first step in obtaining the necessary information. I think cleaning the data is a crucial part of data analysis which we cannot skip. 
If the data we provide is incorrect, the outcomes are not something we can rely on or use with ease. Its going to mess up the entire process and time, resources spent of analyzing raw, uncleaned data could potentially be very costy for a business at the end. Providing clean data to the customer can be also beneficial for the overall process and business development.
When cleaning data, it would be beneficial to select a small portion of data and work on it to see the possible outcomes rather than try working on the entore dataset. This could potentially save some time and struggle if something gets accdentally deleted.
Cleaning data coulb be separated in few steps:
 - 1. Analyze and call quiries to see any possible dublicates
 - 2. Delete the doubliocates by using DELETE FROM
 - 3. Cleaning strings
 - 4. Making sure data is repesented in the correct format. Exmpl: date format for a date; product price and etc
 - 5. Aligh columns, makesure the formatting is clear and consistent, readble 
 - 6. Check to see how cleaned data is related to the set goals

Queries:
Below, provide the SQL queries you used to clean your data.

DELETE FROM
    all_sessions a
        USING all_sessions b
WHERE
    a."fullVisitorId" < b."fullVisitorId"
    AND a."fullVisitorId" = b."fullVisitorId";

    >>>>> Convert string to date format
    SELECT TO_DATE(date, 'YYYYMMDD') as date
    FROM all_sessions

    >>>>> select cast("productRevenue"/1000000 as real) AS "newproductRevenue"
    FROM all_sessions

    >>>>> Removing NULL values since they provide no useful information

    ALTER table all_sessions
    DROP COLUMN searchkeyword, product_refund_amount, item_quality, item_revenue 