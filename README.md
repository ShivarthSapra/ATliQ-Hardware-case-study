# ATliQ-Hardware-case-study
# PROBLEM STATEMENT:
Our case study is based on a computer hardware business which is facing challenges in dynamically changing market. Sales director decides to invest in data analysis project and  would like to build power BI dashboard that can give him real time sales insights. 

As sales directory of atliQ hardware has decided to invest in data analysis project he did a meeting with IT director, data analytics team to come up with a plan. We will use AIMS grid to define purpose and success
criteria of this project.

**PURPOSE**

To Unlock sales insights that are not visible before sales team for decision support & automate them to reduced mannual time spent in data gathering

**STAKE-HOLDERS**

* Sales Director
* Marketing team
* Customer service team
* Data and Analytics team 
* IT

**END RESULT**

An automate dashboard providing quick and latest sales insights in order to support data driven decision.

**SUCCESS CRITERIA**

Dashboard uncovering sales  order insights with latest data available, sales team able to make  better decision and prove 10% cost saving of total spend.

**END RESULT**

An automate dashboard providing quick and latest sales insights in order to support data driven decision.

**SUCCESS CRITERIA**

Dashboard uncovering sales  order insights with latest data available, sales team able to make  better decision and prove 10% cost saving of total spend.

## Data Analysis Using SQL

1. Show all customer records

   `SELECT * FROM customers;`

2. Show total number of customers

   `SELECT count(*) FROM customers;`

3. Show transactions for Chennai market (market code for chennai is Mark001

   `SELECT * FROM transactions where market_code='Mark001';`

4. Show distrinct product codes that were sold in chennai

   `SELECT distinct product_code FROM transactions where market_code='Mark001';`

5. Show transactions where currency is US dollars

   `SELECT * from transactions where currency="USD"`

6. Show transactions in 2020 join by date table

   `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

7. Show total revenue in year 2020,

   `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
   
8. Show total revenue in year 2020, January Month,

   `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

9. Show total revenue in year 2020 in Chennai

   `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_cod
    e="Mark001";`

### Data Analysis Using Power BI

 **Formula to create norm_amount column**

   `= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`
