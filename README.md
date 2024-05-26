## Data Pipeline for Walmart E-commerce Sales Analysis

This report details the creation of a data pipeline to process and analyze e-commerce sales data from a multinational retail corporation, Walmart. 

## Project Goals

* Extract data from various sources (SQL and Parquet)
* Transform and clean the data
* Aggregate data for monthly sales analysis
* Load the cleaned and aggregated data into CSV files

### Data Pipeline Steps

The data pipeline is implemented through a series of custom Python functions:

1. **extract()**: This function retrieves data from the `grocery_sales` table and the `extra_data.parquet` file. It combines them into a single DataFrame named `merged_df`.

2. **transform()**: This function takes the `merged_df` as input and performs data cleaning and transformation steps:
    * Fills missing numerical values (implementation method not specified).
    * Adds a new column named "Month".
    * Filters for rows where weekly sales exceed $10,000.
    * Drops unnecessary columns.
    * Stores the cleaned data in a DataFrame named `clean_data`.

3. **avg_monthly_sales()**: This function calculates monthly average sales from the `clean_data` DataFrame. It:
    * Groups data by "Month".
    * Calculates the average sales for each month (rounded to 2 decimals).
    * Stores the aggregated data in a DataFrame named `agg_data`.

4. **load()**: This function saves the cleaned and aggregated data into CSV files:
    * `clean_data` is saved as `clean_data.csv` without an index.
    * `agg_data` is saved as `agg_data.csv` without an index. 

5. **validation()**: This function verifies the existence of the two CSV files (`clean_data.csv` and `agg_data.csv`) in the current working directory.

### Implementation Details

Note that the specific implementation details for filling missing values are not provided in the project description. You'll need to choose a suitable method (e.g., mean imputation, median imputation) based on your data characteristics.

### Benefits of the Data Pipeline

This data pipeline automates the process of extracting, transforming, and loading e-commerce sales data. It ensures consistent data processing and facilitates further analysis of monthly sales trends within the Walmart corporation.

### Next Steps

The cleaned and aggregated data in CSV format can now be used for further analysis and visualization. You can explore creating charts to visualize monthly sales trends, identify seasonal patterns, or compare sales performance across different product categories.
