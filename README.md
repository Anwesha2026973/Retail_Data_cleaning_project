# Retail Sales Data Cleaning Using Python

## Project Overview
This project demonstrates a practical data-cleaning workflow using Python and Pandas on the UCI Online Retail dataset.

The objective was to identify data-quality issues, remove exact duplicate records, investigate missing and unusual values, and prepare a separate dataset for ordinary product-sales analysis.

## Dataset
- **Source:** UCI Machine Learning Repository — Online Retail
- **Original records:** 541,909
- **Original columns:** 8

The dataset contains invoice numbers, product codes, descriptions, quantities, invoice dates, unit prices, customer IDs, and countries.

## Tools Used
- Python
- Pandas
- Google Colab

## Data Cleaning Steps
1. Inspected the dataset structure, data types, and missing values.
2. Identified and removed 5,268 exact duplicate rows.
3. Investigated missing customer IDs and product descriptions.
4. Examined cancelled invoices, negative quantities, zero prices, and unusual price values.
5. Created a separate dataset for ordinary product-sales analysis.
6. Validated the cleaned data and exported the outputs as CSV files.

## Project Results

| Metric | Result |
|---|---:|
| Original dataset rows | 541,909 |
| Rows after duplicate removal | 536,641 |
| Duplicate rows remaining in master dataset | 0 |
| Rows in product-sales dataset | 524,878 |
| Missing descriptions in product-sales dataset | 0 |
| Non-positive quantities in product-sales dataset | 0 |
| Non-positive prices in product-sales dataset | 0 |

## Data Cleaning Approach

The cleaned master dataset retains records with missing customer IDs, missing descriptions, returns, cancelled invoices, and unusual price values unless removed as exact duplicates.

The product-sales dataset applies additional filters:
- Excludes cancelled invoices identified by invoice numbers beginning with `C`.
- Excludes rows with missing product descriptions.
- Retains only positive quantities and positive unit prices.

These filters prepare the data for ordinary product-sales analysis. They do not calculate net sales including returns and cancellations.

## Project Outputs
- `retail_cleaned_master.csv` — deduplicated master dataset.
- `retail_product_sales.csv` — filtered dataset for product-sales analysis.
- `data_quality_report.csv` — data-quality metrics.

## Key Learnings
- Identifying missing values and duplicate records.
- Cleaning and validating data using Pandas.
- Investigating unusual transaction records before deciding how to handle them.
- Applying business rules appropriate to an analysis objective.
- Exporting datasets and documenting data-quality results.

## Data Source
UCI Machine Learning Repository: [Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

## Disclaimer
This is a learning and portfolio project. The product-sales dataset is a filtered subset for analysis, not a fully reconciled financial ledger.
