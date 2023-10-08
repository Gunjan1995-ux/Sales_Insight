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
The data used in this project is from 2017 to 2020 and was downloaded from kaggle [link](https://www.kaggle.com/datasets/mohdsuhailmasroor/atliq-hardware/data). The data consists of the following tables
1. customers: stores the information of customers
2. dates: stores the dates
3. markets: stores the information of various offices
4. products: stores the information of the products
5. transactions: stores the main base of the dataset where all the tables join and calculate the total revenue and sales

#### Data Security and Integrity

No personal information of customers and employees is involved.
The original file is backed up with an extra copy in another folder.

## Process

**Step1.** I create a dataset in MySQL named "sales" and imported all the tables.



