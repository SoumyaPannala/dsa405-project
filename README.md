# dsa405-project

This repository contains the files for the DSA 405 project, including raw and cleaned data, project notebooks, and supporting documentation.

## Project Overview

This project analyzes animal intake and outcome records from the Austin Animal Center to investigate the research question: **What animal characteristics are associated with faster placement into a home?** The analysis found that dogs generally had shorter placement times than cats, and median placement time decreased across older age groups. Return to Owner cases had substantially shorter median times than adoptions. These findings describe associations in the available records and do not establish causation.

## Data Sources

Both datasets were published by the City of Austin through the Austin Animal Services Open Data Portal.

- **Austin Animal Center Intakes:** [Dataset](https://data.austintexas.gov/d/wter-evkm)
- **Austin Animal Center Outcomes:** [Dataset](https://data.austintexas.gov/d/9t4d-g238)

Both datasets are listed as **Public Domain**. The City of Austin requests attribution to the City and Austin Animal Services. Additional source and access information is documented in `data/raw/Sources.md`.

## Project Work

The project includes data acquisition, inspection, cleaning, integration, and analysis.

- **Data Audit & Cleaning:** Inspects the datasets, identifies data quality issues, and prepares the intake data for analysis.
- **Data Acquisition:** Retrieves the Outcomes dataset from the City of Austin's public CSV export. The acquisition code uses a one-second delay, request timeout, HTTP error handling, response validation, and local caching to avoid unnecessary repeated downloads.
- **Data Integration:** Combines intake and outcome records using animal IDs and chronological event numbers. The integration process uses one-to-one merge validation to prevent unintended row multiplication and reports unmatched records.
- **Verification:** Uses assertions and record-count comparisons to check the results of the integration and final dataset.

## How to Run

The project uses Python notebooks and libraries including Pandas, NumPy, and Requests.

1. Open the repository in Jupyter Notebook or Google Colab.
2. Run the notebooks in order: **P1, P2, and P3**.
3. Run each notebook from top to bottom, starting with a fresh kernel.

The notebooks cover the following steps:

- **P1:** Introduces the research question, identifies the data sources, and examines their suitability for the project.
- **P2:** Audits and cleans the intake data.
- **P3:** Acquires the outcome data, joins the datasets, performs the final cleaning, and conducts the analysis.

The raw and intermediate data files are included in `data/raw`. The notebooks use these files where applicable, including the cached Outcomes dataset, to avoid unnecessary repeated downloads. Run the data preparation and cleaning steps before the integration and analysis steps when starting from the beginning.

**P4** contains the written project synthesis report.

## Repository Structure

```text
dsa405-project/
│
├── data/
│   └── raw/
│       ├── Sources.md
│       ├── austin_animal_center_intakes_raw.csv.gz
│       ├── austin_animal_intakes_clean.csv.gz
│       └── austin_animal_outcomes.csv
│
├── .gitignore
├── DSA405_002_FA26_P1_spannal
├── DSA405_002_FA26_P2_spannal
├── DSA405_002_FA26_P3_spannal
├── DSA405_002_FA26_P4_spannal
└── README.md
```




