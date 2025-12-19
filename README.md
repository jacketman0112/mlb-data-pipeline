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

## Notes
- Database ingestion (MySQL) is planned as the next step and will be executed in a local environment.
