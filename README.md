# YouTube Data Analysis with AWS Data Engineering

## Project Description

This GitHub project demonstrates a comprehensive data engineering pipeline for analyzing YouTube data using various AWS services, including S3, IAM, AWS Glue, Athena, Lambda, and QuickSight. The process encompasses data ingestion, cleaning, transformation, and visualization, leveraging AWS's scalable and efficient cloud infrastructure.

### Project Workflow

1. **Data Ingestion:**
   - **AWS S3:** All raw data is uploaded to Amazon S3 using the AWS CLI from the root account.
   - **Data Organization:** Raw data is organized into different S3 buckets based on file extensions: CSV files are stored in one folder, and JSON files in another.

2. **Data Cleaning:**
   - **AWS Lambda:** Lambda functions are deployed and tested to clean the data. This involves converting CSV files into Parquet format and storing the cleaned data in a separate S3 bucket.

3. **Data Transformation:**
   - **AWS Glue:**
     - **Crawlers:** AWS Glue Crawlers are used to catalog the raw data and create a metadata database.
     - **ETL Jobs:** ETL jobs are created to transform raw CSV files into Parquet format. The transformation includes partitioning the data by regions for optimized querying and storage.
     - **Database Creation:** A cleaned data database is established in AWS Glue, containing the transformed and partitioned data.

4. **Data Processing and Analytics:**
   - **AWS Glue Jobs:** Additional Glue jobs are created to join the cleaned raw data and raw statistics, transforming them into analytic-ready Parquet files.
   - **AWS Athena:** Athena is used to query the final analytics data stored in the S3 bucket. This enables interactive SQL queries on the large datasets.

5. **Data Visualization:**
   - **AWS QuickSight:** The final analytics data is visualized using AWS QuickSight. A dashboard is created to provide insights and visual representations of the YouTube data.

### Additional Features

- **IAM Roles and Policies:** IAM roles and policies are configured to grant the necessary permissions to access S3, CloudWatch, and other AWS services securely.

### Project Components

- **S3 Buckets:**
  - Raw data storage (CSV and JSON)
  - Cleaned data storage (Parquet format)
  - Analytics data storage

- **Lambda Functions:** For data cleaning and format conversion.

- **AWS Glue:**
  - Crawlers for data cataloging
  - Databases and tables for raw and cleaned data
  - ETL jobs for data transformation and partitioning

- **Athena Queries:** For querying the final dataset.

- **QuickSight Dashboard:** For data visualization.

### QuickSight Dashboard

You can view the QuickSight dashboard created for this project [here](https://us-east-1.quicksight.aws.amazon.com/sn/dashboards/8c6a945d-641a-47b3-8aeb-48c416077969).

This project exemplifies a robust data engineering pipeline leveraging AWS services to process and analyze YouTube data efficiently. The integration of these services provides a scalable solution for handling large datasets and deriving meaningful insights through data visualization.




![dashboard](https://github.com/har-shu/YouTube-Data-Analysis-with-AWS-Data-Engineering/assets/71369996/fba2de47-6d08-4e13-8ea1-007f7376b8a9)





## Repository Structure

```
.
├── lambda_functions/
│   ├── data_cleaning.py
│   └── format_conversion.py
├── glue_jobs/
│   ├── etl_transform.py
│   └── join_statistics.py
├── athena_queries/
│   ├── query1.sql
│   └── query2.sql
├── quicksight_dashboard/
│   └── dashboard_definition.qs
├── iam_policies/
│   ├── s3_full_access.json
│   └── cloudwatch_access.json
└── README.md
```

### Getting Started

1. **Upload Data to S3:**
   - Use AWS CLI to upload your YouTube data to the designated S3 buckets.

2. **Deploy Lambda Functions:**
   - Deploy the Lambda functions for data cleaning and format conversion.

3. **Set Up AWS Glue:**
   - Create crawlers, databases, and ETL jobs in AWS Glue for data transformation.

4. **Run Athena Queries:**
   - Use Athena to query the transformed data stored in the S3 analytics bucket.

5. **Visualize with QuickSight:**
   - Create and share your QuickSight dashboard for data visualization.

This repository provides all the necessary scripts and configurations to set up and run the YouTube data analysis pipeline on AWS. Follow the instructions in the README.md file to get started with your data engineering project.
