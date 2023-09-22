# Spotify End-to-End ETL DataEngineering Project

### Description
In this project, we will build ETL (extract, Transform, Load) pipeline using the Spotify API on AWS. It will extract data from Spotify API about the top 50 global songs, transform into desired format and store into an AWS data store.

### AWS Services used:
- Lamda
- S3 bucket
- Cloudwatch
- Glue
- Athena

### The pipeline is divided into 3 parts:
1. Extract
2. Transform
3. Load

🔶 Extract
1. Data Extraction from Spotify API using Python on local using Spotipy.
2. Using AWS Lambda to deploy the extraction function - spotify_api_data_extract.
3. Applied Cloud Watch to automate and run Triggers every 1 min.
4. Stored the extracted raw data in S3 Bucket in to_processed folder.

🔶 Transform
1. Added S3 triggers when new data comes in bucket, whenever new data comes, it will 2nd function for further transformation. 
2. Applied Data Transformation using AWS Lambda on function - spotify_transformation_load_function
3. Storing the transformed data in S3 Bucket in different folders(Album, Artist, Song) and also moves data from to_processed to processed folder.

🔶 Load
1. Used Glue Crawler to infer schemas whenever there is new data in S3 Bucket.
2. Create AWS Glue Data Catalog to manage the Metadata Repository.
3. Use Amazon Athena to query and analyse the final dataset for desired information.

