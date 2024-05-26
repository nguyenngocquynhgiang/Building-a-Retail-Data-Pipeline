## Data Pipeline for Walmart E-commerce Sales Analysis

This report details the creation of a data pipeline to process and analyze e-commerce sales data from a multinational retail corporation, Walmart. 
### Detailed website about the project: 
https://sites.google.com/view/building-a-retail-datapipeline/general?authuser=3
## Project Goals

* Extract data from various sources (SQL and Parquet)
* Transform and clean the data
* Aggregate data for monthly sales analysis
* Load the cleaned and aggregated data into CSV files

### Data Pipeline Steps

The data pipeline is implemented through a series of custom Python functions:
![image](https://github.com/nguyenngocquynhgiang/Building-a-Retail-Data-Pipeline/assets/135851627/0ff52bcc-0571-4a81-9b65-d4d19dceb527)

1. **extract()**: This function retrieves data from the `grocery_sales` table and the `extra_data.parquet` file. It combines them into a single DataFrame named `merged_df`.
![image](https://github.com/nguyenngocquynhgiang/Building-a-Retail-Data-Pipeline/assets/135851627/4e8cd9de-f96e-499c-99bb-3e16bfd03209)

2. **transform()**: This function takes the `merged_df` as input and performs data cleaning and transformation steps:
    * Fills missing numerical values (implementation method not specified).
    * Adds a new column named "Month".
    * Filters for rows where weekly sales exceed $10,000.
    * Drops unnecessary columns.
    * Stores the cleaned data in a DataFrame named `clean_data`.
![image](https://github.com/nguyenngocquynhgiang/Building-a-Retail-Data-Pipeline/assets/135851627/235cfc32-4345-479e-bb32-1dfe54938ce6)

3. **avg_monthly_sales()**: This function calculates monthly average sales from the `clean_data` DataFrame. It:
    * Groups data by "Month".
    * Calculates the average sales for each month (rounded to 2 decimals).
    * Stores the aggregated data in a DataFrame named `agg_data`.
![image](https://github.com/nguyenngocquynhgiang/Building-a-Retail-Data-Pipeline/assets/135851627/a651a97e-5656-437d-8330-42658b3257c9)

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

## Data Pipeline Requirements

This section outlines the requirements for building the data pipeline for Walmart e-commerce sales analysis:

**Data Sources:**

* **SQL Database:** Contains a table named `grocery_sales` holding relevant sales data. (No specific engine required)
* **Parquet File:**  A file named `extra_data.parquet` containing additional data points.

**Software Dependencies:**

* Python (version not specified, but libraries like Pandas will likely be used)

**Functionality:**

* **Data Extraction:**
    * The `extract()` function should combine data from the `grocery_sales` table and the `extra_data.parquet` file into a single DataFrame.
* **Data Transformation:**
    * The `transform()` function should clean and transform the data by:
        * Filling missing numerical values (method to be chosen based on data characteristics).
        * Adding a new column named "Month".
        * Filtering for rows with weekly sales exceeding $10,000.
        * Dropping unnecessary columns.
        * Storing the cleaned data in a DataFrame named `clean_data`.
* **Data Aggregation:**
    * The `avg_monthly_sales()` function should calculate monthly average sales:
        * Group data by the "Month" column.
        * Calculate the average sales for each month (rounded to 2 decimals).
        * Store the aggregated data in a DataFrame named `agg_data`.
* **Data Loading:**
    * The `load()` function should save the cleaned and aggregated data into CSV files:
        * `clean_data` DataFrame saved as `clean_data.csv` without an index.
        * `agg_data` DataFrame saved as `agg_data.csv` without an index.
* **Data Validation:**
    * The `validation()` function should verify the existence of the two generated CSV files in the current working directory. 

**Additional Considerations:**

* Error handling should be implemented to gracefully handle potential issues during data extraction, transformation, or loading.
* Documentation for each function is recommended to improve code maintainability and understanding.

**Deliverables:**

* Python script containing the implemented functions for data pipeline execution.
* Two CSV files: `clean_data.csv` and `agg_data.csv` containing the cleaned and aggregated data, respectively.

