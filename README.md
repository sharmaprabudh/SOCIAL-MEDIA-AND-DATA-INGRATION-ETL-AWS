# 📱 Social Media Data Integration ETL Pipeline (AWS Glue)

**Author:** Prabudh Sharma  
🔗 **GitHub Profile:** https://github.com/sharmaprabudh  
📂 **Project Repository:** https://github.com/sharmaprabudh/SOCIAL-MEDIA-AND-DATA-INGRATION-ETL-AWS  
💼 **LinkedIn:** https://www.linkedin.com/in/prabudh-sharma-680235205/

---

## 📌 Project Overview
This project demonstrates an **AWS Glue ETL pipeline for integrating Twitter and blog datasets** to generate actionable social media insights. The workflow uses **Amazon S3, AWS Glue Crawlers, Data Catalog, IAM, and Visual ETL** to automate ingestion, cleansing, joining, and aggregation of social media data.

The final output helps analyze:
- User activity trends
- Tweet counts
- Hashtag extraction
- Earliest engagement timestamps
- Social media sentiment-ready insights

---

## 🎯 Objectives
- Build a scalable ETL workflow using AWS Glue
- Integrate Twitter and blog data using `user_id`
- Remove duplicate fields
- Extract hashtags using Regex
- Generate user-level engagement summaries
- Store output in Amazon S3 for SQL querying

---

## 🏗️ AWS Services Used
- **Amazon S3** → Raw and processed data storage
- **AWS Glue Crawlers** → Schema discovery
- **AWS Glue Data Catalog** → Metadata tables
- **AWS Glue Visual ETL** → Data transformation
- **AWS IAM** → Secure role management
- **Amazon S3 Select** → SQL querying output files

---

## 📂 Project Workflow

### 1️⃣ Data Ingestion
Created input S3 bucket:
- `etl-twitter-blog`

Created folders:
- `etl-social-media`
- `blog-data`

Uploaded:
- Twitter dataset CSV
- Blog dataset CSV

Created output bucket:
- `etl-cep-output`

---

### 2️⃣ AWS Glue Catalog Setup
Created database:
- `social_media_data`

Configured classifiers:
- `twitter_data`
- `blog_data`

Created crawlers:
- `tweet-crawl`
- `blog-crawler`

This generated Glue catalog tables automatically.

---

### 3️⃣ ETL Transformation Pipeline

### ✅ Join Transformation
- Joined Twitter and Blog datasets
- Join type: **Inner Join**
- Join key: `user_id`

### ✅ Drop Fields
- Removed duplicate `user_id`

### ✅ Regex Extraction
Extracted hashtags from tweet text:
- Source column: `tweet_text`
- Regex: `#(\w+)`
- New column: `hashtags`

### ✅ Aggregation
Grouped by:
- `right_user_id`

Calculated:
- **Count of tweet_id**
- **Minimum timestamp**

---

## 🔄 ETL Flow Architecture
```text
Twitter CSV + Blog CSV
          ↓
      Glue Crawlers
          ↓
   Glue Catalog Tables
          ↓
   Inner Join on user_id
          ↓
   Remove Duplicates
          ↓
   Extract Hashtags
          ↓
   Aggregate by User
          ↓
   Store Output in S3
```

---

## 📊 Output
Final processed output stored in:
- `etl-cep-output`

Used **S3 Select SQL** for querying processed data.

Generated analytics:
- User tweet counts
- Earliest activity timestamps
- Extracted hashtag patterns

---

## 🚀 Business Value
- Improved social media data integration
- Better customer engagement insights
- Hashtag trend discovery
- Faster sentiment-ready analytics
- Marketing strategy optimization
- Serverless and scalable ETL workflow

---

## 🧰 Tech Stack
- AWS Glue
- Amazon S3
- AWS IAM
- Glue Crawlers
- Data Catalog
- Visual ETL
- Regex Extractor
- SQL

---

## 📈 Future Enhancements
- Add sentiment analysis using AWS Comprehend
- Connect with Athena for advanced SQL
- Build QuickSight dashboards
- Automate scheduled ETL jobs
- Add real-time Twitter stream ingestion

---

## 👨‍💻 Author
**Prabudh Sharma**  
🔗 GitHub: https://github.com/sharmaprabudh  
📂 Repository: https://github.com/sharmaprabudh/SOCIAL-MEDIA-AND-DATA-INGRATION-ETL-AWS  
💼 LinkedIn: https://www.linkedin.com/in/prabudh-sharma-680235205/

---

## ⭐ Project Outcome
Successfully built a **production-style AWS Glue ETL pipeline** that integrates Twitter and blog data, extracts hashtags, and generates **user-level engagement insights for trend analysis and marketing intelligence**.
