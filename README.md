# MLB Data Pipeline (ETL)

This project demonstrates a simple data engineering pipeline using the official MLB Stats API.

## Project Overview
- Extract MLB game data from the official MLB Stats API
- Handle multiple dates and no-game days safely
- Transform nested JSON data into structured tabular format
- Export cleaned data as CSV for downstream usage (e.g., database ingestion)

## Data Source
- MLB Stats API: https://statsapi.mlb.com/

## Pipeline Flow

MLB API (JSON)
↓
Python (requests, pandas)
↓
Data Cleaning & Validation
↓
CSV Output



## Output
- `data/mlb_games_2024_07_01_to_07_07.csv`
- 93 MLB games collected

## Tech Stack
- Python
- pandas
- requests
- Google Colab

- ## Database Ingestion (Local MySQL)

After validating the ETL process in Google Colab and exporting the cleaned data as CSV,  
the data is ingested into a local MySQL database using Python and SQLAlchemy.

### Details
- Database: MySQL (local)
- Schema: mlb_db
- Table: mlb_games
- Primary Key: gamePk

### Ingestion Flow
CSV
→ Python (pandas, SQLAlchemy)
→ Local MySQL
→ Verification via MySQL Workbench

### Verification
- Row count check (`COUNT(*)`)
- System table validation (`information_schema.tables`)
- Primary key constraint prevents duplicate game records

This step completes the full ETL pipeline in a local environment before cloud deployment.

## Cloud Deployment (GCP)

The ETL pipeline was successfully deployed to Google Cloud SQL (MySQL).
Data was ingested from Python into Cloud SQL via public IP with authorized networks,
and verified using Cloud SQL Studio (`COUNT(*)`).



## Notes
- Database ingestion (MySQL) is planned as the next step and will be executed in a local environment.
