# Hotel-Revenue-Analysis
# Hotel Revenue Analysis (2018-2020) - Milestone 1

📌 Project Overview
This project transforms raw hotel booking and marketing data into a structured Star Schema. Milestone 1 covers the end-to-end ETL process, from handling regional date formats to normalizing dimensions for high-performance business intelligence.

🏗️ Data Architecture: The Star Schema
The model separates quantitative metrics (Facts) from descriptive attributes (Dimensions) to ensure 1:N relational integrity.

1. Fact Table
- Raw Fact: The central hub containing ADR, Revenue, Calculated Profit, and Foreign Keys.

2. Dimension Tables
- hotel: Hotel/Branch details mapped via hotel_id.
- date: Standardized calendar utilizing a numeric date_key.
- room: Pricing tiers (Standard, Deluxe, Premium) mapped via room_id.
- customer: Unique guest profiles based on demographics and country.

🛠️ ETL & Data Engineering Steps

Data Consolidation & Cleaning
- Regional Date Handling: Resolved DD/MM/YYYY format issues using Locale-based parsing (English-UK).
- Error Handling: Sanitized children/babies columns and filled null profit values via Calculated Profit logic.
- Index Generation: Assigned unique IDs (hotel_id, room_id, customer_id) to replace text-based joins.

Feature Engineering
- Room Categorization: Dynamically assigned Room Categories based on ADR spend thresholds.
- Stay Segmentation: Engineered 'Booking Duration' and 'Stay Type' (Short/Medium/Long) to analyze operational efficiency.
- Financial Logic: Applied cost mapping and market segment discounts.

🔗 Relational Integrity
- Strict ID Joining: In accordance with best practices, the model is strictly joined via Numeric/Alphanumeric IDs. Redundant text columns were removed from the Fact table to optimize performance and ensure a lean Star Schema.
