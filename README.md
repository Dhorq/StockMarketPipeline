# Stock Market Data Pipeline

## Description

This project is a data pipeline that fetches stock market data from the **Yahoo Finance API**, stores the raw data as JSON in a **MinIO Data Lake**, then converts the JSON files into CSV format. The CSV files are retrieved from MinIO and loaded into **PostgreSQL** as a data warehouse. Additionally, the data stored in PostgreSQL can be visualized using **Metabase** to create interactive dashboards.

---

## Pipeline Architecture

1. **Data Ingestion**
   Scheduled data extraction from Yahoo Finance API using Apache Airflow.

2. **Data Lake (MinIO)**
   Raw data is stored in JSON format in MinIO for scalable, cost-effective object storage.

3. **Data Transformation**
   JSON files in MinIO are converted into CSV format for easier loading and processing.

4. **Data Warehouse (PostgreSQL)**
   CSV files are fetched from MinIO and loaded into PostgreSQL via Airflow for analysis and reporting.

5. **Dashboard (Metabase)**
   Data in PostgreSQL is visualized using Metabase, enabling easy monitoring and business insights.

---

## Technologies Used

- **Apache Airflow**: Workflow orchestration and scheduling.
- **Yahoo Finance API**: Stock market data source.
- **MinIO**: Object storage for the data lake.
- **PostgreSQL**: Relational database for data warehousing.
- **Metabase**: Dashboard and data visualization platform.
- **Python**: Main programming language for pipeline and data transformation.

---

## How to Run

1. Set up MinIO and create a bucket for data storage.
2. Run Apache Airflow and configure connections to MinIO and PostgreSQL.
3. Execute the DAGs to:

   - Extract data from Yahoo Finance.
   - Store JSON data in MinIO.
   - Convert JSON to CSV and save back to MinIO.
   - Load CSV data from MinIO into PostgreSQL.

4. Connect Metabase to PostgreSQL to build dashboards.
