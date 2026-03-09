
# Global Superstore Sales Analysis

## Project Overview

This project presents a comprehensive analysis of the **Global Superstore dataset**, focusing on sales performance, profitability, customer behaviour, and regional trends between **2011 and 2014**.

The analysis was conducted using **Power BI**, where the raw dataset was transformed into a structured **star schema data model** consisting of fact and dimension tables. Interactive dashboards were then developed to visualise key performance indicators and uncover meaningful business insights.

The objective of this project is to demonstrate how **data modelling, business intelligence tools, and data visualisation techniques can convert raw transactional data into actionable insights that support business decision making**.


# Business Objectives

The analysis aims to answer several important business questions:

* Which products generate the highest revenue and profit?
* Which regions and countries contribute most to overall sales?
* Who are the most valuable customers?
* How do sales and profit change over time?
* Which product categories perform best?
* Where are opportunities to improve profitability and performance?


# Dataset Information

The dataset used in this project is the **Global Superstore dataset**, sourced from Kaggle.

### Dataset Characteristics

* **Total rows:** 51,290
* **Total columns:** 24
* **Time period:** 2011 – 2014
* **Data type:** Retail transactional data

### Key Data Fields

| Column        | Description                      |
| ------------- | -------------------------------- |
| Order ID      | Unique identifier for each order |
| Order Date    | Date the order was placed        |
| Ship Date     | Date the order was shipped       |
| Customer Name | Customer name                    |
| Segment       | Customer segment                 |
| Country       | Customer country                 |
| City          | Customer city                    |
| Category      | Product category                 |
| Sub-Category  | Product subcategory              |
| Product Name  | Product description              |
| Sales         | Revenue generated                |
| Quantity      | Number of units sold             |
| Discount      | Discount applied                 |
| Profit        | Profit generated                 |


# Data Modelling

To improve analytical performance and maintain a scalable structure, the dataset was transformed into a **star schema data model**.

The model separates transactional data from descriptive data by organising the dataset into **fact and dimension tables**, which is a best practice commonly used in **data warehousing and business intelligence systems**.


# Fact Table

## Fact_Sales

The **Fact_Sales** table stores the core transactional data for each sales order.

Each record represents a sales transaction and contains the measurable business metrics used in the analysis.

### Key Fields

| Column        | Description                      |
| ------------- | -------------------------------- |
| Order ID      | Unique identifier for each order |
| Product Key   | Links to product dimension       |
| Customer Key  | Links to customer dimension      |
| Territory Key | Links to territory dimension     |
| Order Date    | Date of the order                |
| Ship Date     | Shipping date                    |
| Sales         | Total revenue                    |
| Quantity      | Units sold                       |
| Discount      | Discount applied                 |
| Profit        | Profit generated                 |

This table acts as the **central table in the model**, connecting to multiple dimension tables.


# Dimension Tables

## Dim_Product

Contains detailed product information.

| Column          | Description                  |
| --------------- | ---------------------------- |
| Product Key     | Unique identifier            |
| Product Name    | Name of the product          |
| Subcategory Key | Links product to subcategory |


## Dim_Subcategory

Provides intermediate classification for products.

| Column           | Description                 |
| ---------------- | --------------------------- |
| Subcategory Key  | Unique identifier           |
| Subcategory Name | Product subcategory         |
| Category Key     | Links to category dimension |


## Dim_Category

Represents the highest level of product classification.

| Column        | Description       |
| ------------- | ----------------- |
| Category Key  | Unique identifier |
| Category Name | Product category  |

## Dim_Customer

Stores information about customers.

| Column        | Description       |
| ------------- | ----------------- |
| Customer Key  | Unique identifier |
| Customer Name | Customer name     |
| Segment       | Customer segment  |


## Dim_Territory

Contains geographical data used for regional analysis.

| Column        | Description                  |
| ------------- | ---------------------------- |
| Territory Key | Unique identifier            |
| Country       | Country                      |
| Region        | Geographic region            |
| Market        | Global market classification |


## Dim_Calendar

The calendar table enables time-based analysis.

| Column   | Description       |
| -------- | ----------------- |
| Date Key | Unique identifier |
| Date     | Calendar date     |
| Month    | Month             |
| Quarter  | Quarter           |
| Year     | Year              |


# Data Model Relationships

The model follows a **star schema structure**, where the **Fact_Sales** table connects to each dimension table using foreign keys.

Relationships include:

* Fact_Sales → Dim_Product
* Fact_Sales → Dim_Customer
* Fact_Sales → Dim_Territory
* Fact_Sales → Dim_Calendar

Additionally, the product hierarchy is structured as:

* Dim_Product → Dim_Subcategory
* Dim_Subcategory → Dim_Category

This structure allows analysis at multiple levels, from **product categories down to individual products**.


# Tools and Technologies

The project was developed using the following tools:

| Tool                     | Purpose                                      |
| ------------------------ | -------------------------------------------- |
| Power BI                 | Data visualisation and dashboard development |
| DAX                      | Creation of calculated measures              |
| Power Query / M Language | Data transformation                          |
| Kaggle                   | Data source                                  |


# Key Performance Metrics

The analysis generated the following key business metrics:

* **Total Sales:** £12.6 million
* **Total Profit:** £1.5 million
* **Top Customer:** Tom Ashbrook (£35.7K revenue)
* **Most Profitable Product:** Canon imageCLASS 2200 (£24K profit)
* **Most Sold Product:** Sanford Pencil Sharpener, Easy-Erase (849 units)
* **Top Revenue Region:** West & Central
* **Top Revenue Country:** United States (£2.3M revenue)


# Key Insights

## Sales Performance Trends

Sales between 2011 and 2014 demonstrate steady growth with identifiable seasonal patterns. Peak sales occur during **November, December, September, and June**, while **January, February, July, and October** tend to experience lower sales activity.

This pattern suggests that purchasing behaviour is influenced by seasonal demand and major retail periods. Understanding these trends allows organisations to better plan marketing campaigns, manage inventory levels, and forecast future sales performance.


## Customer Segment Performance

The **Consumer segment** is the primary contributor to revenue, generating approximately **£6.5 million in total sales**. Corporate and Home Office segments contribute smaller but still significant portions of revenue.

This indicates that individual retail customers form the organisation’s largest market segment, while business customers present additional opportunities for targeted marketing and specialised service offerings.


## Product Performance

Product analysis reveals that high order volume does not always correspond with the highest profitability.

The **Binder sub-category records the highest number of orders**, demonstrating strong customer demand. However, the **Paper category generates the highest overall profit**, suggesting stronger margins.

The **Canon imageCLASS 2200** stands out as the **most profitable individual product**, generating approximately **£24,000 in profit**.


## Customer Value Contribution

Customer analysis highlights **Tom Ashbrook** as the top revenue-generating customer, contributing approximately **£35,700 in sales** during the analysed period.

Identifying high-value customers allows organisations to implement targeted retention strategies, which can improve long-term revenue stability and customer loyalty.

## Geographic Performance

Geographical analysis indicates that the **United States is the largest revenue-generating country**, contributing approximately **£2.3 million in sales**.

The **West and Central regions generate the highest regional revenue**, while cities such as **New York City** emerge as key commercial hubs.

Strong sales performance is also observed across **North America, Europe, and Asia-Pacific**, demonstrating the organisation’s broad international reach.


## Profitability Performance

Profit margin analysis shows that **China (21.51%) and India (21.36%) have the highest profit margins**, indicating strong profitability within these markets.

Although total sales reached approximately **£13 million**, the organisation narrowly missed its **£14 million target**, suggesting opportunities for further optimisation in pricing strategy, product mix, and regional expansion.


# Business Recommendations

## Align Marketing with Seasonal Demand

Marketing campaigns should be concentrated around high-performing months such as **November, December, September, and June** in order to maximise revenue during peak demand periods.


## Promote High-Margin Products

Products with strong profit margins, such as the **Canon imageCLASS 2200**, should receive increased promotional focus to improve overall profitability.


## Expand High-Profit Markets

Markets demonstrating higher profit margins, particularly **China and India**, present opportunities for further expansion through increased marketing investment and distribution efforts.


## Strengthen Customer Retention

High-value customers should be prioritised through loyalty programmes, personalised marketing campaigns, and improved customer engagement initiatives.


## Improve Sales Target Achievement

Although sales performance is strong, the organisation narrowly missed its sales target. Improving performance in underperforming regions and refining pricing strategies could help close this gap.


## Optimise Product Mix

Products with high order volume but lower margins should be evaluated to ensure they contribute positively to profitability. Adjusting pricing strategies and reducing excessive discounting may improve overall margins.


# Project Structure

```
GlobalSuperStoreAnalysis
│
├── D3424757_Obayangbon_Prosper.pbix
├── D3424757_Obayangbon_Prosper.pdf
└── README.md
```

### Files

**PBIX File**

Contains the Power BI dashboard, including the data model, DAX calculations, and interactive visualisations.

**PDF Report**

Provides a detailed written explanation of the analysis and insights.

**README**

Project documentation describing the methodology, findings, and recommendations.


# How to Use This Project

### 1. Clone the Repository

```
git clone https://github.com/Prosper-Obayangbon/GlobalSuperStoreAnalysis.git
```

### 2. Open the Dashboard

Open the `.pbix` file using **Power BI Desktop**.

### 3. Explore the Dashboard

Interact with the dashboard to analyse:

* Sales trends
* Product performance
* Customer behaviour
* Regional sales distribution

### 4. Review the Report

Open the PDF report to read the detailed explanation of the analysis.


# Skills Demonstrated

This project demonstrates several core data analytics and business intelligence capabilities:

* Data modelling using star schema
* Data transformation and preparation
* Power BI dashboard development
* DAX calculations and measures
* Data visualisation and storytelling
* Exploratory data analysis
* Business insight generation


# Author

**Prosper Obayangbon**

Data Analyst specialising in:

* Power BI
* SQL
* Data Visualisation
* Business Intelligence

GitHub
[https://github.com/Prosper-Obayangbon](https://github.com/Prosper-Obayangbon)


If you want, I can also show you **how to upgrade this README so it looks like a top-tier data analyst GitHub project**, including:

* a **star schema diagram**
* **dashboard screenshots**
* a **portfolio-style layout that impresses recruiters in under 10 seconds**.
