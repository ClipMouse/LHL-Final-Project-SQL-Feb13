Question 1: How many products are marketed specificlly for men? for women?

SQL Queries:

SELECT DISTINCT v2_product_name FROM all_sessions
WHERE v2_product_name ILIKE '%women%'

SELECT DISTINCT v2_product_name FROM all_sessions
WHERE v2_product_name ILIKE '%men%'

Answer: 

83 women's items
77 men's items


Question 2: Explore the relationship between a successfull purchase, and time spent on the website

SQL Queries: 

SELECT * FROM Analytics
WHERE units_sold > 1
ORDER BY timeonsite ASC 
NULLS LAST


Question 3: Which methods of arriving at the site are the most popular?

SQL Queries:

SELECT "channelGrouping", COUNT(full_visitor_id) AS VISITS
FROM all_sessions
GROUP BY "channelGrouping"

Answer:

1.) Organic Search: 8653 visitors

2.) Direct: 2997 visitors

3.) Referral: 2580 visitors


