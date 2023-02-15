What are your risk areas? Identify and describe them.

Risk areas: duplicate values, NULL values interfering with code, insufficiently cleaned data producing inaccurate results

QA Process:
Describe your QA process and include the SQL queries used to execute it.

Validating data after table joins

SELECT COUNT(distinct full_visitor_id)
FROM (SELECT country, city, x.product_sku, y.units_sold, x.full_visitor_id, x.v2_product_name

FROM all_sessions x

LEFT JOIN analytics y

ON x.full_visitor_id = y.full_visitor_id) tmp

vs 

SELECT COUNT(full_visitor_id) FROM all_sessions

Here, there are more instances of full_visitor_id in the table than there are distinct full_visitor_id, meaning that some Full_visitor_id is duplicated. Duplication can be explained in part by multiple site visits / purchases. 

*******************************************************


