# Dataset

## Dataset Used

This project uses the **AdventureWorks** dataset for educational and portfolio analysis.

The dataset contains business information covering:

- Customers
- Products
- Product Categories
- Product Subcategories
- Sales
- Returns
- Territories
- Calendar dates

## Data Preparation

The sales data was provided across multiple yearly tables:

- AdventureWorks_Sales_2015
- AdventureWorks_Sales_2016
- AdventureWorks_Sales_2017

These sales tables were combined into a single **Sales 2015-2017** table for analysis.

The data was then prepared using **Power Query** before building the Power BI data model.

## Data Modelling

The Power BI model connects the main business tables to support analysis across:

- Sales and customers
- Sales and products
- Products and product categories
- Products and product subcategories
- Sales and territories
- Sales and calendar dates
- Returns and relevant dimensions

## Data Quality

Data validation was performed during the modelling and dashboard development process to check relationships, calculations and unexpected results.

Unmatched customer records were also investigated and handled at the visual-analysis level where appropriate.

## Source Data

The raw dataset is **not included in this repository**.

The dataset is used for educational and portfolio purposes, while the repository focuses on the Power BI model, dashboard development, DAX measures and business analysis.
