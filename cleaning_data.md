What issues will you address by cleaning the data?

Cleaning data helps to remove and/or reduce inaccuracies, duplicaties, missing values, formatting inconsistency, software incompatability, etc. for the purposes of more accurate, manageable, and clear data. 

Manual cleaning performed: renamed columns for consistency and to avoid errors caused by capitalization, changed column data type to allow for operations in excess of their existing capability (int changed to bigint). Deleted rows with no data


Queries:
Below, provide the SQL queries you used to clean your data.



To adjust for prices being 1,000,000 times too large:

SELECT unit_price/1000000 as true_unit_price FROM analytics

-- this creates a new column with the corrected unit price


To find specific values (such as NULL or 0):

SELECT * FROM analytics

WHERE city is NULL

-- to identify missing values 


To find values containing a term:

SELECT * FROM all_sessions

WHERE city LIKE '%no%'

-- This returned all the cities with value "(not set)" and "not available in demo dataset" 

-- Wildcard % allows for any string regardless of capitalization


Search for a term with even greater flexibility: 

SELECT * FROM all_sessions

WHERE v2_product_name ILIKE '%Google%'

-- this returned all products spelled "Google" or "google" or any other combination of upper and lower case letters

To filter out duplicates:

SELECT DISTINCT 

To SELECT despite letter casing:

ILIKE






