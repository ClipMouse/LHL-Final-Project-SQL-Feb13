Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:

SELECT country, city, "totalTransactionRevenue" FROM all_sessions

ORDER by "totalTransactionRevenue" ASC



SELECT SUM ("totalTransactionRevenue"), country FROM all_sessions

GROUP by country ORDER by SUM ("totalTransactionRevenue")




Answer:

Top countries: USA, Israel, Australia, Canada, Switzerland
Top cities: San Francisco, Sunnyvale, Atlanta, Palo Alto, Tel Aviv-Yafo


**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:

SELECT city, country, AVG(units_sold) 
FROM all_sessions x
LEFT JOIN analytics y
ON x.full_visitor_id = y. full_visitor_id
GROUP BY city, country
ORDER BY AVG(units_sold) DESC NULLS LAST

Answer: data output points to the USA being the top consumer by far.

**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:

SELECT country, city, x.product_sku, y.units_sold, x.full_visitor_id, x.v2_product_name

FROM all_sessions x

LEFT JOIN analytics y

ON x.full_visitor_id = y.full_visitor_id

ORDER BY units_sold DESC

NULLS LAST


Answer: The United States accounts for the overwhelming majority of sales. There are cities in the US which are top in sales as well, but their data (or its data) is only listed as "not available in demo dataset." This would be the most notable pattern - that data for "city" is missing in many rows with significant sales numbers




**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:

SELECT country, city, x.product_sku, y.unit_price, y.units_sold, (y.unit_price * y.units_sold)/1000000 as net_revenue, x.full_visitor_id, x.v2_product_name

FROM all_sessions x

LEFT JOIN analytics y

ON x.full_visitor_id = y.full_visitor_id

GROUP BY country, city, x.product_sku, y.unit_price, y.units_sold, net_revenue, x.full_visitor_id, x.v2_product_name
ORDER BY net_revenue DESC

NULLS LAST



Answer:







