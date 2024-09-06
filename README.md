# Snowflake Project
This project involves analyzing competitors of "RareBurger" in the New York area by querying data from Snowflake Marketplace. The SQL code provided selects relevant data, such as location, region, postal code, and various spending metrics, from both the "RareBurger" restaurant's revenue data and a sample dataset of other NYC restaurants. By filtering the competitors using the CATEGORY_TAGS field to include only those tagged as 'Burger', the query effectively identifies and aggregates information on competing burger establishments in the area.

### Here's a breakdown of the SQL code:
```SQL
SELECT LOCATION_NAME, REGION, POSTAL_CODE, STREET_ADDRESS, RAW_TOTAL_SPEND, RAW_NUM_TRANSACTIONS, RAW_NUM_CUSTOMERS, ONLINE_SPEND, MEDIAN_SPEND_PER_TRANSACTION, MEDIAN_SPEND_PER_CUSTOMER 
FROM
THERAREBURGER.PUBLIC.MONTHLY_REVENUE
UNION SELECT LOCATION_NAME, REGION, POSTAL_CODE, STREET_ADDRESS, RAW_TOTAL_SPEND, RAW_NUM_TRANSACTIONS, RAW_NUM_CUSTOMERS, ONLINE_SPEND, MEDIAN_SPEND_PER_TRANSACTION, MEDIAN_SPEND_PER_CUSTOMER 
FROM
FREE_SAMPLE_CROSS_SHOPPING_INSIGHTS__NYC_RESTAURANTS.PUBLIC.SPEND_CROSS_SHOPPING_SAMPLE 
WHERE
CATEGORY_TAGS LIKE '%Burger%';
```

### Data Selection: 
The code selects several key metrics that are important for analyzing competitors:

- LOCATION_NAME: The name of the restaurant.
- REGION, POSTAL_CODE, STREET_ADDRESS: Location details of the restaurants.
- RAW_TOTAL_SPEND, RAW_NUM_TRANSACTIONS, RAW_NUM_CUSTOMERS: Raw financial and customer data.
- ONLINE_SPEND: Amount spent online.
- MEDIAN_SPEND_PER_TRANSACTION, MEDIAN_SPEND_PER_CUSTOMER: Median spending metrics for further insight.

### Data Sources:

The first SELECT statement pulls data from the MONTHLY_REVENUE table, which likely contains data specific to "RareBurger".
The second SELECT pulls data from the SPEND_CROSS_SHOPPING_SAMPLE table, which contains data from other NYC restaurants, but filters for those related to the 'Burger' category using the CATEGORY_TAGS field.
Combining Data:

The UNION operation is used to combine the data from these two sources, creating a unified dataset that includes both "RareBurger" and its competitors.
Dashboard and Report:

The resulting data could be visualized in a dashboard, likely designed to compare "RareBurger" with its competitors in terms of spending, customer transactions, and other financial metrics. This analysis would help identify how "RareBurger" stands in the competitive landscape and inform strategic decisions.
This approach is a solid way to gain insights into market competition and customer behavior in the context of the burger restaurant industry in New York.

## [Click here to go to the Snowflake Project](https://app.snowflake.com/nlvcceo/zvb57327/#/rareburger_benchmark-dE3g63C3v)


![Screenshot](https://github.com/snmhoque123/snowflake_Project/blob/main/Screenshot%202024-09-02%20155947.png)
