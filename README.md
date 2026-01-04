# airbnb-analytics-data-warehouse
End-to-end data warehouse and analytics pipeline for Airbnb listings, pricing, and availability using BigQuery and Looker Studio.

## Overview

This project demonstrates an end-to-end data engineering workflow using modern analytics tools. Starting from a raw Airbnb CSV dataset, I designed and implemented a star-schema data model, performed data cleaning and transformations using Python (Pandas), loaded the processed data into Google BigQuery, and built interactive dashboards in Looker Studio for business insights.

The goal of this project was to simulate how a data engineer / analytics engineer would structure, transform, and expose data for analytics and visualization in a production-like environment.


## Tech Stack

- **Data Source:** Raw Airbnb listings CSV
- **Languages & Libraries:** Python, SQL, Pandas
- **Cloud & Data Warehouse:** Google Cloud Platform (GCP), BigQuery
- **Visualization:** Looker Studio
- **Development:** Jupyter Notebook

**Data Dimension Modelling using a star schema design in lucid.app**
<img width="1247" height="666" alt="image" src="https://github.com/user-attachments/assets/4e591326-be7c-4694-b1e6-1682217f3e3d" />


# ETL Workflow
1️⃣ Extract

- Imported raw Airbnb listing data from CSV
- Inspected schema, data types, and missing values

2️⃣ Transform

- Removed duplicate records
- Standardized categorical values (e.g. neighbourhood group names)
- Cleaned numeric fields such as price and service fees
- Created dimension tables and a fact table following a star schema:

fact_listings
dim_host
dim_room_type
dim_neighbourhood
dim_cancellation_policy
dim_listing_details

- Generated surrogate keys for dimension tables
- Ensured referential integrity between fact and dimension tables
- Optimized transformations to avoid memory-intensive joins

3️⃣ Load

- Loaded transformed tables into BigQuery using pandas_gbq
- Used replace-strategy for iterative development
- Structured dataset for direct consumption by BI tools

⭐ Data Model (Star Schema)

Fact Table contains the following fields:
fact_listings
listing_id
host_id
neighbourhood_id
room_type_id
cancellation_policy_id
price
service_fee
minimum_nights
number_of_reviews
reviews_per_month
review_rate_number
calculated_host_listings_count
availability_365
construction_year
last_review
instant_bookable

Dimension Tables are of the following:

dim_host

dim_room_type

dim_neighbourhood

dim_cancellation_policy

dim_listing_details

This structure enables efficient analytics, scalable joins, and clean semantic modeling for BI tools.


# 📊 Analytics & Visualization (Looker Studio)

Built interactive dashboards to analyze:

- Distribution of listings by room type
- Geographic distribution of listings using geo maps
- Average price by room type and neighbourhood
- Availability and review patterns
- Borough-level listing concentration using color-coded maps

The dashboards are designed for exploratory analysis and business-friendly insights.


#💡 Key Learnings

- Designing analytics-friendly schemas is more important than raw transformations
- Large joins in Pandas can cause memory issues if not modeled correctly
- Cloud warehouses like BigQuery simplify analytics and scaling
- BI tools work best when data is clean, well-modeled, and aggregated appropriately
