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

This included first checking the how data looks. Used SQL queries as follows:

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/1.JPG?raw=true)

As I am using MySQL and PowerBI side by side. I connected MySQL to the PowerBI Desktop. 

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/10.png?raw=true)

After this, I loaded all the tables from the database. This load option will connect with the SQL and pull all the records into the PowerBI environment.

The schema below shows the relationship between the tables, this schema is known as **Star Schema**

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/11.JPG?raw=true)

Found a few unwanted data in **'markets'** tables, as the sales manager is only interested in the Indian market.
![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/2.JPG?raw=true)

Now, I did some cleaning the unwanted data I found in the **'markets'** table is removed.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/12.JPG?raw=true)

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/13.JPG?raw=true)

In the **'transactions'** table, I found some unwanted values like the sales amount column has '-1' and the currency column has 'USD' value. 

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/4.JPG?raw=true)

Removed sales amount values less than or equal to '0' for **' transaction table'**.

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/14.JPG?raw=true)

Also converted USD currency to INR

![alt text]( https://github.com/Gunjan1995-ux/Sales_Insight/blob/main/screenshots/15.JPG?raw=true)

Similarly checked other columns in the **transactions** column, and nothing needs to be changed.



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




