# 🚖 Uber Trip Analytics using AWS S3 & Snowflake

## 📌 Project Overview
This project demonstrates an **end-to-end cloud data ingestion pipeline** using **AWS S3** and **Snowflake**.  
Uber trip CSV files are stored in AWS S3 and securely loaded into Snowflake using **Storage Integration** and **External Stages** for analytics and reporting.

---

## 🏗️ Architecture
1. CSV files stored in **AWS S3**
2. Data loaded into **Snowflake** using **Storage Integration**
3. Tables created and populated using `COPY INTO`


---

## 🛠️ Tools & Technologies
- **AWS S3** – Cloud object storage
- **AWS IAM** – Secure role-based access
- **Snowflake** – Cloud data warehouse
- **SQL** – Data definition and loading

---

## 📂 Dataset
The following datasets are used:
1. **Location Table** – Pickup and drop-off location details
2. **Uber Trip Details** – Trip time, distance, fare, surge fee, and payment type

Files are stored in an AWS S3 bucket.

---

## 🔐 AWS–Snowflake Integration
- Created an **IAM Role** for Snowflake
- Configured **Storage Integration** in Snowflake
- Restricted access using `STORAGE_ALLOWED_LOCATIONS`
- Created **External Stage** linked to S3

---

## 🧩 Snowflake Objects Created
- Database: `POWERBI`
- Schema: `POWERBI_DATA`
- Tables:
  - `LOCATION_TABLE`
  - `UBER_TRIP_DETAILS`
- Stage:
  - `S2`
- Storage Integration:
  - `POWERBI_INT`

---

## 📜 SQL Implementation
| Script | Purpose |
|------|--------|
| `integration.sql` | Creates storage integration with AWS |
| `schema_tables.sql` | Creates database, schema, and tables |
| `load_from_aws.sql` | Loads CSV data from S3 using COPY INTO |

---

## 🔄 Data Loading Example
COPY INTO UBER_TRIP_DETAILS
FROM @S2/Uber_Trip_Details.csv
FILE_FORMAT = (TYPE='CSV' FIELD_DELIMITER=',' SKIP_HEADER=1)
ON_ERROR='CONTINUE';

---

##  🚀 Key Learnings
- AWS S3 bucket management  
- IAM role-based access for Snowflake  
- Snowflake storage integrations and external stages  
- Secure and scalable cloud data ingestion  
- SQL-based analytics in Snowflake  

---

## Screenshorts
<img width="1919" height="971" alt="Screenshot 2026-01-29 004554" src="https://github.com/user-attachments/assets/2d744210-6b23-4c72-a721-86a28583d495" />
<img width="1896" height="964" alt="Screenshot 2026-01-29 004451" src="https://github.com/user-attachments/assets/66afc8f9-f559-4e1e-bf09-afc844d72e9a" />
<img width="1915" height="966" alt="Screenshot 2026-01-29 004514" src="https://github.com/user-attachments/assets/6345933c-eb1f-49fa-a069-ac80f67a0ff2" />

