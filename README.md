
![372435439-08d61b3f-3ebb-4a8b-a9a3-11a4d23da6e9](https://github.com/user-attachments/assets/0337dfb7-eacb-4521-b90a-25011a535e62)

**Weather Data ETL Pipeline**

This project demonstrates a complete ETL (Extract, Transform, Load) pipeline for real-time weather data using OpenWeatherMap API, Apache Airflow, Amazon S3, and Snowflake. The pipeline automates the extraction, transformation, and loading of weather data into Snowflake for analysis and querying.

### Overview
The ETL pipeline performs the following steps:

- **Extract**: Retrieves real-time weather data from OpenWeatherMap API.
- **API Health Check**: Uses a dedicated DAG to ensure the API is functional.
- **Store**: Saves raw weather data to an S3 bucket.
- **Transform**: Processes the raw data using a transformation DAG.
- **Load**: Loads the transformed data into a Snowflake stage, where it is automatically ingested into a Snowflake table for further analysis.

### Tech Stack
- **OpenWeatherMap API**: Source of real-time weather data.
- **Apache Airflow**: Orchestrates the ETL process with three DAGs:
  - **DAG 1**: Validates API functionality.
  - **DAG 2**: Extracts and uploads raw data from the API to S3.
  - **DAG 3**: Transforms data and triggers Snowpipe to load it into Snowflake.
- **Amazon S3**: Stores raw data.
- **Snowflake**: Data warehouse for querying and analyzing weather data.
- **Snowpipe**: Automates data ingestion from S3 into Snowflake tables.

### Workflow
1. **Data Extraction**: A DAG retrieves real-time weather data in JSON format from OpenWeatherMap.
2. **API Health Check**: The first DAG ensures the API is responsive before executing further tasks.
3. **Data Transformation**: A second DAG processes the raw weather data for analytics.
4. **Data Loading**: The transformed data is uploaded to S3, and Snowpipe automatically ingests it into Snowflake for analysis.
5. **Snowflake Queries**: Once ingested into Snowflake, the data can be queried to analyze weather patterns and trends.

This pipeline ensures the seamless extraction, transformation, and loading of weather data, allowing for real-time analytics in Snowflake.
