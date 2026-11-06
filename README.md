# dsa405-project

This repository contains the files for the DSA 405 project, including raw data, cleaned data, notebooks, a cleaning log, and other documentation relevant to the project.

## Project Focus & Data

This project analyzes animal intake and outcome data from the Austin Animal Center. The data is published by the City of Austin through Austin Animal Services.

The project uses two datasets:

- **Intakes:** Animal intake records from the Austin Animal Center.
- **Outcomes:** Animal outcome records from the Austin Animal Center, obtained through the City of Austin Open Data Portal.

The original and acquired data files are stored in the `data/raw` folder. Cleaned data and other project outputs are stored in their respective project folders.

### Data Sources

- [Austin Animal Center Intakes](https://data.austintexas.gov/)
- [Austin Animal Center Outcomes – Dataset 9t4d-g238](https://data.austintexas.gov/d/9t4d-g238)

## Project Work

The project includes data acquisition, inspection, cleaning, and integration.

- **Data Audit & Cleaning:** Inspects the datasets, identifies data quality issues, and prepares the intake data for analysis.
- **Data Acquisition:** Retrieves the Outcomes dataset from the City of Austin's public CSV export. The acquisition code uses a one-second delay, request timeout, HTTP error handling, response validation, and local caching to avoid unnecessary repeated downloads.
- **Data Integration:** Combines intake and outcome records using animal IDs and chronological event numbers. The integration process uses a one-to-one merge validation to prevent unintended row multiplication and reports unmatched records.
- **Verification:** Uses assertions and record-count comparisons to check the results of the integration.

## How to Run

Open the relevant project notebook in Jupyter Notebook or Google Colab and run the cells from top to bottom.

The notebooks use Python and libraries including Pandas, NumPy, and Requests. The acquisition code saves the downloaded Outcomes data in `data/raw` and uses the cached file on subsequent runs when available.

Run the data preparation and cleaning steps before the integration notebook when working from the beginning of the project. The integration notebook also uses the cleaned Intakes dataset stored in the repository.


