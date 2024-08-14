# GDP Extraction and Transformation Project
Extract, Transfrom and Load GDP Data

## Project Overview
I was recruited to play the role of a Junior Data Engineer for an international firm that is expanding its business globally. The primary task was to create an automated script that extracts and processes data on the Gross Domestic Product (GDP) of countries as reported by the International Monetary Fund (IMF). This data will be used by the organization to track global economic trends and inform business decisions.

The data is sourced from the following URL:
[IMF GDP Data](https://web.archive.org/web/20230902185326/https://en.wikipedia.org/wiki/List_of_countries_by_GDP_%28nominal%29)

## Objectives
The project involves creating a Python script named `etl_project_gdp.py` to perform the following tasks:

1. **Data Extraction**: 
   - Retrieve the list of countries and their GDPs from the provided URL.
   
2. **Data Transformation**:
   - Convert GDP values from Million USD to Billion USD and round them to two decimal places.
   
3. **Data Loading**:
   - Save the transformed data into a CSV file named `Countries_by_GDP.csv`.
   - Store the data in a SQLite database file named `World_Economies.db` under the table `Countries_by_GDP` with attributes `Country` and `GDP_USD_billion`.
   
4. **Query Execution**:
   - Run a query on the database to display only the countries with a GDP greater than 100 billion USD.
   
5. **Logging**:
   - Log the entire process, including data extraction, transformation, and loading, with appropriate timestamps in a log file named `etl_project_log.txt`.

## Setup Instructions

### Prerequisites
To successfully run the script, i ensured that the following Python libraries are installed:

- `requests`: For accessing data from the URL (bundled with Python).
- `bs4`: Contains BeautifulSoup, used for web scraping.
- `pandas`: For data processing, storage, and database communication.
- `sqlite3`: Required for database server connection (bundled with Python).
- `numpy`: For mathematical rounding operations.
- `datetime`: For timestamp extraction and logging (bundled with Python).

### Installing Libraries

```bash
python3.11 -m pip install pandas
python3.11 -m pip install numpy
python3.11 -m pip install bs4
```

### Initial Setup

1. **Create Script File**:
   - To navigate to the project directory and create the script file `etl_project_gdp.py`:
     ```
     \home\project\etl_project_gdp.py
     ```

2. **Initialize Variables**:
   - Defining the entities in the script:

     - **URL**: The source of the GDP data.
       ```python
       url = 'https://web.archive.org/web/20230902185326/https://en.wikipedia.org/wiki/List_of_countries_by_GDP_%28nominal%29'
       ```

     - **table_attribs**: The attributes for the initial DataFrame.
       ```python
       table_attribs = ['Country', 'GDP_USD_millions']
       ```

     - **db_name**: Name of the database file.
       ```python
       db_name = 'World_Economies.db'
       ```

     - **table_name**: Name of the database table.
       ```python
       table_name = 'Countries_by_GDP'
       ```

     - **csv_path**: Path for the CSV file.
       ```python
       csv_path = 'Countries_by_GDP.csv'
       ```

3. **Log Initialization**:
   - Log the initialization process in the `etl_project_log.txt` file.

## Running the Script
After setting up the environment and initializing the variables, i ran the `etl_project_gdp.py` script to perform the ETL process and generate the required outputs.

## Demonstrating Success
To demonstrate the success of the script, i ensured that:
- The `Countries_by_GDP.csv` file is correctly populated.
- The `Countries_by_GDP` table in the `World_Economies.db` database contains the expected data.
- The query results displaying countries with a GDP greater than 100 billion USD are accurate.
- The `etl_project_log.txt` file captures the process with timestamps.

This project automates the extraction, transformation, and loading of GDP data, ensuring the organization stays up-to-date with the latest global economic information.
