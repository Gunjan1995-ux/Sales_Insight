# Sales_Insight

## Introduction
This project aims to provide sales insight for a hardware and peripheral device supply company "AtliQ Hardware". 

As their business is growing, the company's sales manager is facing issues in tracking sales in this dynamic market. In order to analyze the sales, he asked the regional managers to assist him. He wants to visualize the data to get a clear picture of sales.

## Ask
The problem is that the conversations that are happening are verbal. Hence, the regional managers are sugarcoating the facts and the manager of the company does not get a clear picture of the facts. Even after knowing that the sales are declining, he cannot do anything because he does not have a clear picture of the sales. After asking about the sales records the regional managers gave him a big Excel file which made it very hard for him to understand the business sales. All that that he wants to know is:

What are the weakest areas the company needs to focus on to increase sales and improve the declination?
And a simple, understandable, and digestive insight into sales, a dashboard through which he can go and look at the real data.

Project planning using AIMS grid –
It is a project management tool which consists of four components:
1. Purpose
2. Stakeholders
3. End Results
4. Success Criteria

For this project, end result would be a dashboard, and success criteria would be increasing the sales using cost optimization, giving a clear idea while saving the manager's time.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/grid.JPG?raw=true)

## Prepare
The data used in this project is from 2017 to 2020 and was downloaded from [here](https://codebasics.io/resources/sales-insights-data-analysis-project). The dataset is also available on Kaggle [link](https://www.kaggle.com/datasets/mohdsuhailmasroor/atliq-hardware/data). The data consists of the following tables
1. customers: stores the information of customers
2. dates: stores the dates
3. markets: stores the information of various offices
4. products: stores the information of the products
5. transactions: stores the main base of the dataset where all the tables join and calculate the total revenue and sales

I used MySQL and PowerBI for this project.

#### Data Security and Integrity

No personal information of customers and employees is involved.
The original file is backed up with an extra copy in another folder.

## Process

The data had to be processed before it was ready for analysis. This includes cleaning, transforming, and constantly validating the data to ensure it is clean and ready for analysis.

This included first checking the how data looks. Used SQL queries as follows using simple SQL statements like "Select * from table name;"

As I am using MySQL and PowerBI side by side. I connected MySQL to the PowerBI Desktop. 

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/10.png?raw=true)

After this, I loaded all the tables from the database. 

The schema below shows the relationship between the tables, this also is known as **Star Schema**.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/11.JPG?raw=true)

Now, I found a few unwanted data in **'markets'** tables, as the sales manager is only interested in the Indian market.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/2.JPG?raw=true)

I did some cleaning, I removed this unwanted data in PowerBI.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/12.JPG?raw=true)

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/13.JPG?raw=true)

In the **'transactions'** table, I found some unwanted values like the sales amount column has '-1' and the currency column has 'USD' value. 

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/4.JPG?raw=true)

Removed sales amount values less than or equal to '0' for **' transaction table'**.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/14.JPG?raw=true)

Also converted USD currency to INR

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/15.JPG?raw=true)

Also, found that there were duplicate currencies. That could be a special character present at the end of the string. Used **clean** from PowerBI to remove those characters.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/16.JPG?raw=true)

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/17.JPG?raw=true)

After this, also removed duplicates from the **transactions** table.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/18.JPG?raw=true)

Checked if there were any transactions for New York and Paris, as the sales manager only is looking for transactions done in India. None were found.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/3.JPG?raw=true)

## Analyze

For some basic analysis, I used SQL to find out transactions of a particular year which is joined by the date table.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/5.JPG?raw=true)

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/6.JPG?raw=true)

I can calculate the total revenue of a particular year with the following queries

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/7.JPG?raw=true)

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/8.JPG?raw=true)

I can also find out the business you did in a particular year (eg. 2020 ) and city (eg. Mumbai their market code is Mark002)

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/8.JPG?raw=true)

In PowerBI, two measures were created to calculate **revenue** and **sales quantity** which show the total revenue and total sales made, respectively.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/21.JPG?raw=true)

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/22.JPG?raw=true)

Next, Revenue in each city is made, by using columns "market_name" and "currency in INR".

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/23.JPG?raw=true)

And also made an analysis of the total number of sale quantities made in the Market.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/24.JPG?raw=true)

Find out the top 5 customers based on the revenue made for the company.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/25.JPG?raw=true)

And also made an analysis of the top 5 products that were sold in the market.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/26.JPG?raw=true)

Next, I made an analysis of the revenue made by the company over the past 4 years (2017,2018,2019,2020).

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/27.JPG?raw=true)

## Vizualization/Share

A dashboard is created according to the requirements. What the company wants to look for and what is more important for the company is taken into consideration and then the dashboard is created. There can be a number of variations to create a dashboard. Generally, the dashboard should look understandable and easy to access.


![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/20.JPG?raw=true)

In this dashboard, we can check revenue and sales by year, month, city,  and customers.
