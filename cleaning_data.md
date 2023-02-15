What issues will you address by cleaning the data?

inaccuracies, duplicaties, missing values, formatting consistency, software incompatability

e.g. changed productSKU to product_sku to avoid errors


Queries:
Below, provide the SQL queries you used to clean your data.

To filter out duplicates:
SELECT DISTINCT 

To SELECT despite letter casing
ILIKE

Wildcard % allows for any string

e.g. SELECT * FROM all_sessions
WHERE v2_product_name ILIKE '%Google%'





