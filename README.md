# Walmart Sales Data Analysis: A Python & MySQL Pipeline

## Project Overview

This project is an end-to-end data analysis pipeline designed to extract valuable business insights from Walmart sales data. By leveraging Python for data manipulation and MySQL for advanced querying, this project explores sales trends, profitability, and customer behavior. It serves as a practical application of data cleaning, feature engineering, and database management.

---

## Workflow & Methodology

### 1. Environment & Workspace Setup
- **Tools**: Visual Studio Code, Python, MySQL.
- **Setup**: Created a structured project environment to efficiently manage data files, scripts, and notebooks.

### 2. Data Acquisition
- **Source**: Walmart Sales Dataset from [Kaggle](https://www.kaggle.com/najir0123/walmart-10k-sales-datasets).
- **Method**: Utilized the Kaggle API to programmatically download the dataset directly into the local `data/` directory using the `kaggle datasets download` command.

### 3. Data Processing & Cleaning (Python)
- **Library Utilization**: Used `pandas` and `numpy` to ingest and inspect the raw data.
- **Cleaning Steps**:
  - Identified and removed duplicate records to ensure data integrity.
  - Handled missing values appropriately (dropping nulls or imputing where necessary).
  - Standardized data types (e.g., casting date strings to `datetime` objects and prices to `float`).
  - Formatted currency and categorical text fields for consistency.

### 4. Feature Engineering
- **Metric Creation**: Engineered a new `Total_Amount` column by multiplying the `unit_price` by `quantity`. This pre-calculated field optimizes downstream SQL aggregations and reporting.

### 5. Database Integration (MySQL)
- **Engine Setup**: Used the `sqlalchemy` and `mysql-connector-python` libraries to establish a connection to a local MySQL server.
- **Data Loading**: Automated the table creation and insertion process, pushing the cleaned Pandas DataFrame directly into the MySQL database.

### 6. Exploratory Data Analysis (SQL)
With the data securely in MySQL, I wrote complex SQL queries to solve specific business questions, including:
- Identifying peak sales periods and customer purchasing trends.
- Calculating revenue and profit margins across different branches and product categories.
- Analyzing the performance of various payment methods.

---

## Tech Stack & Requirements

- **Language**: Python 3.8+
- **Database**: MySQL
- **Core Libraries**: `pandas`, `numpy`, `sqlalchemy`, `mysql-connector-python`
- **Other**: Kaggle API (for data ingestion)

├── data/                  # Contains raw and cleaned CSV datasets
├── sql_queries/           # .sql files containing the business analysis queries
├── notebooks/             # Jupyter notebooks used for initial EDA and testing
└── README.md              # Project documentation
## Future Enhancements

* **Data Visualization**: Connect the MySQL database to a BI tool like Tableau or Power BI to create an interactive dashboard.
* **Pipeline Automation**: Wrap the Python scripts in a scheduler (like cron or Airflow) to simulate a daily batch-processing job.

---

## Acknowledgments

* Dataset provided by Kaggle.
* Project concept inspired by open-source data engineering tutorials and Walmart's retail case studies.
