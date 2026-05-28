# Hong Kong Property Market Analysis

Final-year Data Science & Engineering portfolio project — HKU.

Analyses Hong Kong's residential property market (2020–2024) using PostgreSQL and Tableau.

## Business Questions
1. Which districts offer the best rental yield in 2024?
2. How have transaction prices moved across districts post-COVID (2020–2024)?
3. Is there a correlation between building age and transaction price per sq ft?
4. Which months show the highest/lowest transaction volumes?

## Tech Stack
- **PostgreSQL** — schema + cleaning + analytical queries
- **Python (pandas)** — CSV pre-processing only
- **Tableau** — visualisation / dashboards
- **Git + GitHub** — version control

## Quick Start
```bash
createdb hk_property
psql -d hk_property -f sql/01_schema_setup.sql
psql -d hk_property -f sql/02_data_cleaning.sql
```

## Folder Structure
```
hk-property-analysis/
├── sql/
│   ├── 01_schema_setup.sql      # DDL + raw data load
│   ├── 02_data_cleaning.sql     # NULL handling, type casts, standardisation
│   └── 03_analysis_queries.sql  # Business-question queries (coming next)
├── data/
│   ├── raw/          ← gitignored; download from data.gov.hk (see docs/)
│   └── cleaned/      ← gitignored; produced by Python pre-processing scripts
├── notebooks/
│   └── 01_eda.ipynb             # Exploratory data analysis
├── tableau/
│   └── hk_property.twb          # Tableau workbook (source only, not .twbx)
└── docs/
    └── data_sources.md          # Download instructions & data dictionary
```

## Data Sources
| File | Source | URL |
|------|--------|-----|
| `transactions_20XX.json` | Land Registry | https://data.gov.hk/en-data/dataset/hk-lr-data5-landreg |
| `rental_index_monthly.csv` | RVD | https://data.gov.hk/en-data/dataset/hk-rvd-tsinfo_rvd-property-market-statistics |
| `building_info.csv` | Buildings Dept | https://data.gov.hk/en-data/dataset/hk-bd-opendata-building-information |
| `valuation_list_by_district_csv.csv` | RVD | https://data.gov.hk/en-data/dataset/hk-rvd-tsinfo_rvd-statistical-tables-on-valuation-list-and-government-rent-roll |