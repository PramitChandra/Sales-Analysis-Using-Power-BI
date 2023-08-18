# Sales Insights Data Analysis Project
Instructions to setup mysql on your local computer
Follow step in this video to install mysql on your local computer https://www.youtube.com/watch?v=WuBcTJnIuzo

## Data Analysis Using SQL
- Show all customer records

- SELECT * FROM customers;

- Show total number of customers

- SELECT count(*) FROM customers;

- Show transactions for Chennai market (market code for chennai is Mark001

- SELECT * FROM transactions where market_code='Mark001';

- Show distrinct product codes that were sold in chennai

- SELECT distinct product_code FROM transactions where market_code='Mark001';

- Show transactions where currency is US dollars

- SELECT * from transactions where currency="USD"

- Show transactions in 2020 join by date table

- SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

- Show total revenue in year 2020,

- SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

- Show total revenue in year 2020, January Month,

- SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

- Show total revenue in year 2020 in Chennai

- SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";

## Data Analysis Using Power BI
Formula to create norm_amount column
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)




![Data_Model](https://github.com/PramitChandra/Sales-Analysis-Using-Power-BI/assets/112652928/7413e091-e6c8-4370-a2c2-95ffecd9529c)


![Report_example_1](https://github.com/PramitChandra/Sales-Analysis-Using-Power-BI/assets/112652928/998983e8-3453-4c2b-9d9a-92d4e4638c95)


![Report_example_2](https://github.com/PramitChandra/Sales-Analysis-Using-Power-BI/assets/112652928/b6d69f0a-3959-4ef5-a012-9c3ad49eb1c4)


![Report_example_3](https://github.com/PramitChandra/Sales-Analysis-Using-Power-BI/assets/112652928/ea9ce32d-8076-4acc-ab4f-e758922d2d88)
