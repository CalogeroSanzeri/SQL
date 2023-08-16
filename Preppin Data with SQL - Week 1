-- Preppin' Data week 1 - https://preppindata.blogspot.com/2023/01/2023-week-1-data-source-bank.html

-- Output 1: Total value of transactions by bank 
SELECT
SPLIT_PART(transaction_code,'-',1) AS bank,
SUM(VALUE) AS total_value
FROM PD2023_WK01
GROUP BY bank

-- Output 2: Total values by bank, day of week and type of transaction
SELECT
SPLIT_PART(transaction_code,'-',1) AS bank,
CASE WHEN ONLINE_OR_IN_PERSON = '1' THEN 'Online'
        WHEN ONLINE_OR_IN_PERSON = '2' THEN 'In-Person'
        END AS online_or_in_person,
DAYNAME(DATE(TRANSACTION_DATE, 'dd/MM/yyyy hh24:mi:ss')) as day_of_transaction,
SUM(VALUE) as total_value
FROM PD2023_WK01
GROUP BY 1,2,3

-- Output 3: Total values by bank or customer code
SELECT
SPLIT_PART(transaction_code,'-',1) AS bank,
CUSTOMER_CODE,
SUM(VALUE) as total_value
FROM PD2023_WK01
GROUP BY 1,2
