# Spotify
calable Music Analytics Pipeline (Spotify API + AWS)

# Spotify Top 50 India ETL Pipeline on AWS

This project demonstrates a serverless, automated ETL pipeline that extracts, transforms, and analyzes Spotify playlist data using AWS services.

## 🎯 Objective
To build a cloud-native data pipeline that:
- Extracts song, artist, and album data from the **Top 50 - India** Spotify playlist
- Automates ingestion and transformation processes using AWS Lambda
- Stores data in **Amazon S3**
- Enables structured querying using **Amazon Athena**

---

## 🧩 Tech Stack & Services Used

### ✅ AWS Services
- **Amazon S3**: Stores raw and transformed data (JSON/CSV)
- **AWS Lambda**: Serverless compute to run extract & transform jobs
- **AWS Glue Crawler**: Crawls S3 data and updates the AWS Glue Data Catalog
- **AWS Glue Data Catalog**: Stores metadata for Athena queries
- **Amazon CloudWatch**: Schedules Lambda function weekly
- **Amazon Athena**: Queries structured data using standard SQL

### ✅ Python Libraries
- `spotipy`: Connects to Spotify Web API
- `boto3`: Interacts with AWS services
- `pandas`: Data wrangling and transformation
- `numpy`: Numeric operations

Install dependencies:
```bash
pip install pandas boto3 spotipy numpy
```

---

## 🔁 Execution Flow

1. **Spotify API Connection**
   - Connects using `spotipy` to retrieve metadata for the *Top 50 - India* playlist

2. **CloudWatch Trigger**
   - Weekly trigger initiates Lambda extraction job

3. **Lambda (Extraction)**
   - Fetches raw playlist data and stores it in the `raw/` folder in Amazon S3 as JSON

4. **Lambda (Transformation)**
   - Processes raw data, formats it into clean CSV files, and uploads to `transformed/` folder in S3

5. **Glue Crawler**
   - Automatically crawls transformed S3 folders and updates schemas in the Glue Data Catalog

6. **Athena Queries**
   - Enables SQL-based querying for analytics and reporting

---

## 📊 Example Use Cases

- Identify top artists featured in Top 50 playlists
- Analyze release dates, song duration trends, or album stats
- Feed cleaned data into BI tools like Power BI or QuickSight

---

## 📁 Project Structure
```
spotify-etl/
├── lambda_extract.py
├── lambda_transform.py
├── requirements.txt
├── raw/
│   └── playlist_raw.json
├── transformed/
│   └── songs.csv
├── glue-crawler-config/
├── athena-queries/
└── README.md
```

---

## 🚀 Future Enhancements
- Add streaming data ingestion using AWS Kinesis
- Integrate data visualizations using QuickSight
- Extend to multiple Spotify playlists and genres

---

## 👨‍💻 Author
**Jay Prajapati**  
_Data Engineer | Azure | Databricks | PySpark | AWS_  
[LinkedIn]((https://www.linkedin.com/in/jay-prajapati-5397031b7/)) | [GitHub](https://github.com/jayprajapati22)

---


