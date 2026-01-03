# airbnb-analytics-data-warehouse
End-to-end data warehouse and analytics pipeline for Airbnb listings, pricing, and availability using BigQuery and Looker Studio.

## Overview

This project implements an end-to-end data engineering pipeline to model and analyze Airbnb listings data using a star schema design.

Raw CSV data is ingested, cleaned, and transformed using Python and Pandas, then loaded into Google BigQuery as analytics-optimized fact and dimension tables. The warehouse supports analysis of pricing, availability, host behavior, and neighborhood-level trends.

Interactive dashboards are built in Looker Studio to surface key insights such as demand patterns, price distributions, and booking availability across locations.


## Tech Stack

- **Languages & Libraries:** Python, SQL, Pandas
- **Cloud & Data Warehouse:** Google Cloud Platform (GCP), BigQuery
- **ETL / Orchestration:** Mage
- **Visualization:** Looker Studio
- **Development:** Jupyter Notebook

