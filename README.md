# 🌦️ Weather Domain End-to-End Data Engineering Project on Databricks

## Build a Modern Lakehouse for Weather Analytics using Databricks, Delta Lake, PySpark & Power BI

![Databricks](https://img.shields.io/badge/Databricks-Lakehouse-red)
![PySpark](https://img.shields.io/badge/PySpark-Data%20Engineering-orange)
![Delta Lake](https://img.shields.io/badge/Delta-Lake-blue)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![SQL](https://img.shields.io/badge/SQL-Analytics-green)
![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow)

---

# 📖 Project Overview

This project demonstrates an **end-to-end Data Engineering pipeline** that ingests weather data from multiple REST APIs, processes it using the **Databricks Lakehouse Platform**, and transforms it into business-ready datasets using the **Medallion Architecture (Bronze → Silver → Gold)**.

The platform supports current weather, weather forecasts, historical weather, marine weather, and location lookup for Indian cities, enabling rich analytical dashboards and reporting.

This project showcases modern data engineering best practices including:

- REST API Ingestion
- Incremental Data Loading
- Delta Lake
- Medallion Architecture
- PySpark Transformations
- Data Quality Validation
- Star Schema Modeling
- Databricks Workflows
- Dashboard Analytics
- Performance Optimization

---

# 🏗️ Solution Architecture

```

                 Weather REST APIs
                         │
                         ▼
                Python API Ingestion
                         │
                         ▼
               Bronze Delta Tables
          (Raw JSON API Responses)
                         │
                         ▼
         Silver Delta Tables (Cleaned Data)
                         │
                         ▼
       Gold Delta Tables (Business KPIs)
                         │
                         ▼
              Databricks SQL Warehouse
                         │
                         ▼
              Power BI / Tableau Dashboard

```

---

# 🛠 Technology Stack

| Technology | Purpose |
|------------|----------|
| Databricks | Data Engineering Platform |
| Delta Lake | Data Storage |
| PySpark | Data Processing |
| Python | API Ingestion |
| SQL | Data Analysis |
| Power BI | Dashboard |
| REST APIs | Data Source |
| GitHub | Version Control |

---

# 📡 Data Sources

The project consumes the following Weather API endpoints:

## Current Weather

Provides the latest weather conditions for a location.

Example Metrics

- Temperature
- Humidity
- Pressure
- Wind Speed
- Visibility
- UV Index

---

## Weather Forecast

Forecast weather for upcoming days.

Includes

- Max Temperature
- Min Temperature
- Rain Probability
- Wind Forecast
- Weather Conditions

---

## Historical Weather

Historical weather observations.

Useful for

- Trend Analysis
- Seasonal Analysis
- Temperature Comparison
- Rainfall Analysis

---

## Marine Weather

Provides marine weather information including

- Wave Height
- Sea Temperature
- Wind Speed
- Wind Direction

---

## Historical Marine Weather

Historical marine conditions.

---

## Location Lookup

Location autocomplete for Indian cities.

---

# 📂 Project Structure

```

Weather-Domain-End-to-End-Data-Engineering-Project/

│

├── config/

│ ├── api_config.py

│ └── secrets.py

│

├── notebooks/

│ ├── 01_API_Ingestion

│ ├── 02_Bronze_Load

│ ├── 03_Silver_Transformation

│ ├── 04_Gold_Aggregation

│ ├── 05_Data_Quality

│ └── 06_Dashboard

│

├── src/

│ ├── ingestion/

│ ├── bronze/

│ ├── silver/

│ ├── gold/

│ ├── monitoring/

│ └── utilities/

│

├── sql/

│ ├── bronze.sql

│ ├── silver.sql

│ └── gold.sql

│

├── dashboards/

│ ├── WeatherDashboard.pbix

│ └── screenshots/

│

├── tests/

│

├── docs/

│

├── README.md

│

└── requirements.txt

```

---

# 🥉 Bronze Layer

Purpose

Store raw API responses exactly as received.

No transformations are applied.

### Bronze Tables

```

bronze_current_weather

bronze_weather_forecast

bronze_historical_weather

bronze_marine_weather

bronze_historical_marine_weather

bronze_location_lookup

```

---

# 🥈 Silver Layer

Purpose

Transform raw JSON into structured datasets.

Processing includes

- Schema Validation
- Null Handling
- Duplicate Removal
- Data Standardization
- Business Rules

### Silver Tables

```

silver_current_weather

silver_weather_forecast

silver_historical_weather

silver_marine_weather

silver_location

dim_city

dim_date

dim_weather_condition

```

---

# 🥇 Gold Layer

Business-ready analytical tables.

### Gold Tables

```

gold_weather_summary

gold_temperature_trends

gold_rainfall_summary

gold_city_weather_summary

gold_humidity_summary

gold_wind_summary

gold_marine_summary

gold_forecast_summary

```

---

# ⭐ Star Schema

```

                    dim_city
                        │
                        │
dim_date ───── fact_weather ───── dim_weather_condition
                        │
                        │
                  dim_state

```

---

# 🔄 ETL Pipeline

```

Extract

↓

Weather APIs

↓

Bronze Layer

↓

Data Validation

↓

Silver Layer

↓

Business Aggregation

↓

Gold Layer

↓

Dashboard

```

---

# 📊 Dashboard Overview

## Executive Dashboard

KPIs

- Current Temperature
- Feels Like Temperature
- Humidity
- Pressure
- Wind Speed
- Visibility
- UV Index
- Sunrise
- Sunset

Visualizations

- Weather Summary Cards
- Weather Trend
- Today's Conditions
- Current Weather Map

---

## Weather Trend Dashboard

Charts

- Temperature Trend
- Humidity Trend
- Pressure Trend
- Wind Speed Trend

---

## Forecast Dashboard

Displays

- 7-Day Forecast
- Daily Temperature
- Rain Probability
- Wind Forecast

---

## Historical Dashboard

Compare

- Today
- Yesterday
- Last Week
- Last Month
- Previous Year

---

## Rainfall Dashboard

Includes

- Rainfall Trend
- Monthly Rainfall
- Highest Rainfall Cities
- Rainfall Heatmap

---

## Marine Dashboard

Displays

- Wave Height
- Sea Temperature
- Wind Speed
- Marine Conditions

---

## City Comparison Dashboard

Compare weather across cities.

Example

- Delhi
- Mumbai
- Bengaluru
- Chennai
- Hyderabad
- Kolkata
- Pune
- Ahmedabad

---

# 📋 Data Quality Checks

The pipeline performs

- Duplicate Detection
- Schema Validation
- Null Checks
- Temperature Validation
- Humidity Range Validation
- Wind Speed Validation
- Data Freshness Checks

---

# ⚡ Performance Optimization

The project demonstrates

- Delta Merge
- Partitioning
- OPTIMIZE
- ZORDER
- VACUUM
- Caching
- Predicate Pushdown

---

# 📅 Workflow Orchestration

Databricks Workflows automate

1. API Ingestion
2. Bronze Load
3. Silver Transformation
4. Gold Aggregation
5. Data Quality Checks
6. Dashboard Refresh

---

# 📈 Business KPIs

Example KPIs

- Average Daily Temperature
- Maximum Temperature
- Minimum Temperature
- Average Humidity
- Average Wind Speed
- Total Rainfall
- Rainy Days
- Hottest City
- Coldest City
- Highest Wind Speed
- Weather Distribution

---

# 🚀 Future Enhancements

- Real-Time Streaming Weather
- Air Quality Index Integration
- Weather Alerts
- Satellite Weather Data
- Climate Change Analytics
- Machine Learning Weather Prediction
- Geospatial Analytics
- Automated Monitoring
- CI/CD Pipeline

---

# 💡 Data Engineering Concepts Demonstrated

- REST API Integration
- Incremental Loading
- Medallion Architecture
- Delta Lake
- PySpark
- Databricks Workflows
- SQL Analytics
- Data Quality Framework
- Star Schema
- Slowly Changing Dimensions
- Delta Merge
- Time Travel
- Performance Optimization
- Dashboard Development

---

# 🎯 Skills Demonstrated

- Databricks
- PySpark
- Delta Lake
- SQL
- Python
- REST APIs
- Data Warehousing
- ETL / ELT
- Data Modeling
- Data Quality
- Workflow Orchestration
- Dashboard Development

---

# 📌 Future Scope

This platform can be extended to include

- Air Pollution Data
- AQI Analytics
- Disaster Monitoring
- Flood Prediction
- Cyclone Monitoring
- Weather Alerts
- Climate Analytics
- IoT Weather Sensors
- Streaming Data Pipelines

---

# 📜 License

This project is intended for educational and portfolio purposes.

---

# 👨‍💻 Author

**Your Name**

Data Engineer

**Skills**

- Databricks
- PySpark
- Delta Lake
- SQL
- Python
- Azure Data Engineering
- Power BI

---

⭐ If you found this project helpful, consider giving it a star!
