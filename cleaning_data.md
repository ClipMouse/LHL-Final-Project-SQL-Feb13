What issues will you address by cleaning the data?

Cleaning data helps to remove and/or reduce inaccuracies, duplicaties, missing values, formatting inconsistency, software incompatability, etc. for the purposes of more accurate, manageable, and clear data. 

Queries:
Below, provide the SQL queries you used to clean your data.

To filter out duplicates:

SELECT DISTINCT 

To SELECT despite letter casing:

ILIKE


Wildcard % allows for any string

e.g. SELECT * FROM all_sessions

WHERE v2_product_name ILIKE '%Google%'



To find specific values (such as NULL or 0):

SELECT * FROM analytics

WHERE city IN ("%not%")








