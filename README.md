# Power BI Supermarket Comparison

Compare pricing and affordability across five UK supermarkets using Power BI.

## Table of Contents

- [Overview](#overview)  
- [Data Sources](#data-sources)  
- [Data Model](#data-model)  
- [Folder Structure](#folder-structure)  
- [Getting Started](#getting-started)  
- [Key Dashboards](#key-dashboards)  
- [Technologies](#technologies)  
- [Author](#author)  

## Overview

This project ingests daily product data for the UK’s five largest supermarkets, builds a star-schema model in Power BI, and delivers interactive dashboards that highlight price comparisons, affordability gaps, category trends, and own-brand market share.

## Data Sources

- **Kaggle – UK Supermarket Data**  
  All product information for the UK’s five largest supermarkets, updated daily.  
  https://www.kaggle.com/datasets/declanmcalinden/time-series-uk-supermarket-data  

- Local CSV exports (one per supermarket):  
  - `data/Asda.csv`  
  - `data/Tesco.csv`  
  - `data/Sainsburys.csv`  
  - `data/Morrisons.csv`  
  - `data/Aldi.csv`  

Each file contains: Product Name, Category, Own-Brand flag, Price (£), Price per Unit (£).

## Data Model

Implemented a star-schema design in Power BI:

**Fact Table**  
- SuperMarket_ID  
- Supermarket  
- Product  
- Category  
- OwnBrand  
- Price  
- PricePerUnit  

**Dimension Tables**  
- **SM_Dim**: SuperMarket_ID, Supermarket  
- **Cat_Dim**: Category_ID, Category  
- **OwnBrand_Dim**: OwnBrandFlag, BrandType  

**Relationships**  
- Fact[SuperMarket_ID] → SM_Dim[SuperMarket_ID]  
- Fact[Category] → Cat_Dim[Category]  
- Fact[OwnBrand] → OwnBrand_Dim[OwnBrand]  

## Folder Structure
powerbi-supermarket-comparison/ ├── data/ # Raw CSVs per supermarket │ ├── Asda.csv │ ├── Tesco.csv │ ├── Sainsburys.csv │ ├── Morrisons.csv │ └── Aldi.csv └── Supermarket_Comparison.pbix └── README.md # Project overview and instructions


## Getting Started

1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/powerbi-supermarket-comparison.git

2.Open reports/Supermarket_Comparison.pbix in Power BI Desktop.

3.In Power Query, load the five CSV files from the data/ folder.

4.Configure relationships per the star schema diagram.

5.Refresh data and explore the dashboards.

## Key Dashboards

- **Overview Metrics**  
  Cards showing total products (499), total categories (11) and overall average item price (£4.90).

- **Average Price by Supermarket**  
  A bar chart comparing mean product prices across Tesco, Sainsbury’s, ASDA, Morrisons and Aldi.

- **Total Branded Spend**  
  Bar chart of cumulative spend on branded items at each supermarket (e.g. Tesco £658.69, Sainsbury’s £573.96, etc.).

- **Brand Mix by Store**  
  Stacked bar visual comparing the count (or proportion) of branded vs own-brand products per retailer.

- **Category-Wise Price Distribution**  
  Stacked bars illustrating how each product category contributes to average pricing in each supermarket.

- **Unit Price Comparison (Stores)**  
  Pie chart breaking down the unit-price values across the five supermarkets.

- **Unit Price Comparison (Categories)**  
  Pie chart showing how unit prices vary among different product categories (e.g. fresh food, bakery, drinks, health products, etc.).

## Technologies
Power BI Desktop

Power Query 

DAX (measures & calculated tables)

GitHub

## Author
Suganya Thangam  GitHub | LinkedIn
