What issues will you address by cleaning the data?

Data cleaning is very important step in analyzing, preparing and using the data. Cleaning the data helps to remove any dublicates, corrupted data, missing information or incomplete information within the dataset. Imputing the raw data is the first step in obtaining the necessary information. I think cleaning the data is a crucial part of data analysis which we cannot skip. 
If the data we provide is incorrect, the outcomes are not something we can rely on or use with ease. Its going to mess up the entire process and time, resources spent of analyzing raw, uncleaned data could potentially be very costy for a business at the end. Providing clean data to the customer can be also beneficial for the overall process and business development.



Queries:
Below, provide the SQL queries you used to clean your data.
DELETE FROM
    all_sessions a
        USING all_sessions b
WHERE
    a."fullVisitorId" < b."fullVisitorId"
    AND a."fullVisitorId" = b."fullVisitorId";