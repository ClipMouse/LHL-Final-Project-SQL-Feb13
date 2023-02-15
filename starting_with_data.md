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


Question 3: 

SQL Queries:

Answer:



Question 4: 

SQL Queries:

Answer:



Question 5: 

SQL Queries:

Answer:
