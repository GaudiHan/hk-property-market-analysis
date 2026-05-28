# Hong Kong Property Market Analysis

A data analyst portfolio project exploring Hong Kong's residential property market using SQL and interactive dashboards. Built to demonstrate real-world analytical thinking, SQL proficiency, and business storytelling using publicly available government data.

---

## Business Questions

1. **Which districts offer the best rental yield in 2024?**
2. **How have transaction prices moved across districts post-COVID (2020–2024)?**
3. **What property types (flat, house, villa) dominate each district?**
4. **Is there a correlation between building age and transaction price per sq ft?**
5. **Which months show the highest/lowest transaction volumes — and why?**

---

## Project Structure

```
hk-property-analysis/
│
├── data/
│   ├── raw/                        # Original downloaded files from data.gov.hk
│   │   ├── property_transactions.csv
│   │   ├── rental_index.csv
│   │   └── building_age.csv
│   └── processed/                  # Cleaned, loaded into SQLite/PostgreSQL
│
├── sql/
│   ├── 01_schema_setup.sql         # Create tables and load data
│   ├── 02_data_cleaning.sql        # Handle nulls, standardise district names
│   ├── 03_district_analysis.sql    # Price trends by district
│   ├── 04_rental_yield.sql         # Rental yield calculations
│   ├── 05_building_age.sql         # Age vs price correlation
│   ├── 06_seasonality.sql          # Monthly transaction volume patterns
│   └── 07_window_functions.sql     # Rankings, YoY growth, running totals
│
├── dashboard/
│   └── hk_property_dashboard.twbx  # Tableau workbook (published to Tableau Public)
│
├── insights/
│   └── executive_summary.md        # Key findings written for a non-technical reader
│
└── README.md
```

---

## Data Sources

All data is publicly available and free to download:

| Dataset | Source | Description |
|---|---|---|
| Residential Property Transactions | [data.gov.hk](https://data.gov.hk/en-data/dataset/hk-rvd-rvd014-agreement-sales-purchase) | Sale & purchase agreements by district, 2010–present |
| Private Domestic Rental Index | [Rating and Valuation Dept](https://www.rvd.gov.hk/en/publications/pro-review.html) | Quarterly rental indices by class and district |
| Building Age Data | [data.gov.hk](https://data.gov.hk/en-data/dataset/hk-bd-hkbims-building-age) | Year of completion per building across HK |

> All datasets are provided by the Hong Kong government and are free for public use.

---

## Tech Stack

| Layer | Tool |
|---|---|
| Database | SQLite (local) / PostgreSQL (optional) |
| SQL client | DBeaver or DB Browser for SQLite |
| Visualisation | Tableau Public (free) |
| Scripting | Python (pandas) for initial data cleaning only |
| Version control | Git + GitHub |

---

## SQL Concepts Demonstrated

- `JOIN` across multiple tables (transactions ↔ building age ↔ rental index)
- `GROUP BY` with aggregations (`AVG`, `COUNT`, `SUM`, `MIN`, `MAX`)
- `CTEs` (`WITH` clauses) for multi-step logic
- Window functions: `ROW_NUMBER()`, `RANK()`, `LAG()`, `SUM() OVER()`
- `CASE WHEN` for custom segmentation
- Subqueries for filtering and derived metrics
- Date functions for YoY and MoM comparisons

---

## Key Findings

*(To be updated upon project completion)*

1. **Top rental yield districts** — [placeholder]
2. **Post-COVID price recovery** — [placeholder]
3. **Building age effect** — [placeholder]
4. **Seasonal transaction patterns** — [placeholder]
5. **Best value districts for buyers** — [placeholder]

---

## Dashboard

View the live Tableau dashboard here: **[Tableau Public Link — coming soon]**

The dashboard includes:
- District-level price heatmap (HK Island / Kowloon / New Territories)
- Rental yield ranking bar chart
- Transaction volume trend (2020–2024)
- Price per sq ft vs building age scatter plot
- YoY growth comparison table

---

## How to Run This Project

```bash
# 1. Clone the repo
git clone https://github.com/GaudiHan/hk-property-analysis.git
cd hk-property-analysis

# 2. Download raw data from data.gov.hk (links in Data Sources above)
#    Place CSV files in data/raw/

# 3. Set up the database
sqlite3 hk_property.db < sql/01_schema_setup.sql

# 4. Clean and load data
sqlite3 hk_property.db < sql/02_data_cleaning.sql

# 5. Run analysis queries
sqlite3 hk_property.db < sql/03_district_analysis.sql
# ... and so on for each SQL file
```

---

## About

Built by **Alexander Gaudi Suhandjaja** as part of a Data Analyst portfolio.
- LinkedIn: [linkedin.com/in/gaudihan](https://linkedin.com/in/gaudihan)
- GitHub: [github.com/GaudiHan](https://github.com/GaudiHan)
- Email: gaudihan@gmail.com

---

*Data sourced from Hong Kong government open data. This project is for educational and portfolio purposes only.*
