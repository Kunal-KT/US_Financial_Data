# 📊 Financial Analytics & Power BI Dashboard

An end-to-end **Financial Analytics and Business Intelligence project** built using **Python, Google Drive API, Pandas, and Power BI**.

The project automates the process of extracting financial data from multiple files stored in Google Drive, consolidating the datasets using Python, and transforming the resulting data into an interactive Power BI dashboard for financial analysis and reporting.

---

## 🚀 Project Overview

Financial data is often distributed across multiple **Excel files, CSV files, and Google Sheets**, making manual data collection and consolidation time-consuming.

This project solves that problem by building an automated **ETL pipeline** that:

* Connects to Google Drive using the Google Drive API
* Retrieves financial files from a designated folder
* Supports Google Sheets, CSV, and Excel files
* Downloads and processes the files automatically
* Converts the files into Pandas DataFrames
* Combines multiple datasets into a single consolidated dataset
* Uses the processed data for Power BI reporting and visualization
* Creates an interactive financial analytics dashboard

---

## 🏗️ Project Architecture

```text
                    Google Drive
                         │
                         ▼
                Google Drive API
                         │
                         ▼
              Financial Data Files
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
     Google Sheets      CSV           Excel
          │              │              │
          └──────────────┼──────────────┘
                         ▼
                  Python ETL Pipeline
                         │
                         ▼
                       Pandas
                         │
                         ▼
              Data Consolidation
                         │
                         ▼
                 Combined Dataset
                         │
                         ▼
                     Power BI
                         │
                         ▼
             Financial Dashboard
```

---

## 🛠️ Technologies Used

| Technology                      | Purpose                             |
| ------------------------------- | ----------------------------------- |
| **Python**                      | ETL and data processing             |
| **Pandas**                      | Data manipulation and consolidation |
| **Google Drive API**            | Automated data extraction           |
| **Google Service Account**      | API authentication                  |
| **Requests**                    | File downloading                    |
| **StringIO**                    | Processing CSV data                 |
| **BytesIO**                     | Processing Excel data               |
| **Power BI**                    | Dashboard and reporting             |
| **DAX**                         | Measures and business calculations  |
| **Excel / CSV / Google Sheets** | Data sources                        |

---

## 🔄 ETL Pipeline

### 1. Extract

The Python script connects to Google Drive using the **Google Drive API** and retrieves files from the configured folder.

Supported file formats:

* Google Sheets
* CSV
* Excel `.xlsx`

### 2. Transform

The downloaded files are converted into Pandas DataFrames.

Google Sheets are exported as CSV, while Excel files are read using Pandas.

The individual DataFrames are then consolidated into a single dataset.

Example:

```python
combined_df = pd.concat(
    file_dataframes,
    ignore_index=True
)
```

### 3. Load

The consolidated dataset is prepared for analysis and used as the data source for the Power BI financial dashboard.

---

## 🔐 Google Drive Authentication

The project uses a **Google Cloud Service Account** to authenticate with the Google Drive API.

The required scope is:

```python
SCOPES = [
    "https://www.googleapis.com/auth/drive.readonly"
]
```

The `drive.readonly` permission allows the application to read files without modifying the contents of Google Drive.

### Security

**Service-account credentials must NOT be uploaded to GitHub.**

Do not commit files such as:

```text
*.json
.env
credentials.json
service-account.json
```

Use environment variables or a local credential file instead.

---

## 📁 Recommended Repository Structure

Financial-Analytics-PowerBI/
│
├── README.md - https://github.com/Kunal-KT/US_Financial_Data/blob/main/README.md
│
├── powerbi/
│   └── Financial_Project - https://github.com/Kunal-KT/US_Financial_Data/blob/main/Financial_Project1.pbix
│
├── screenshots/
│   └── dashboard - https://github.com/Kunal-KT/US_Financial_Data/blob/main/Screenshot%202026-09-23%20105305.png

---

## 📦 Python Dependencies

Install the required libraries using:

```bash
pip install -r requirements.txt
```

Example `requirements.txt`:

```text
pandas
requests
openpyxl
google-api-python-client
google-auth
google-auth-httplib2
google-auth-oauthlib
```

---

## ▶️ How to Run the Project

### Step 1 — Clone the repository

```bash
git clone https://github.com/your-username/financial-analytics-powerbi.git
```

### Step 2 — Navigate to the project

```bash
cd financial-analytics-powerbi
```

### Step 3 — Install dependencies

```bash
pip install -r requirements.txt
```

### Step 4 — Configure Google Cloud Authentication

Create a Google Cloud Service Account and download the credentials JSON file.

Keep the credentials file outside the GitHub repository.

### Step 5 — Configure the Google Drive Folder

Update the folder configuration using an environment variable or local configuration:

```python
FOLDER_ID = "YOUR_GOOGLE_DRIVE_FOLDER_ID"
```

### Step 6 — Run the ETL script

```bash
python python/google_drive_etl.py
```

The script will:

```text
Connect to Google Drive
        ↓
Find financial files
        ↓
Download supported files
        ↓
Read files using Pandas
        ↓
Combine DataFrames
        ↓
Create consolidated dataset
```

### Step 7 — Open Power BI

Open the Power BI file:

```text
powerbi/Financial_Project1.pbix
```

Refresh the dataset and explore the financial dashboard.

---

## 📊 Power BI Dashboard

The Power BI component is designed to provide an interactive view of financial information through:

* KPI cards
* Financial metrics
* Trend analysis
* Category analysis
* Interactive filters
* Data visualizations
* Business performance analysis

The dashboard can be used to explore financial patterns and support data-driven decision-making.

---

## 💡 Business Problem

Financial information can be stored across multiple sources and file formats.

Manually downloading, combining, and preparing these files can lead to:

* Repetitive work
* Data inconsistencies
* Manual errors
* Difficult reporting processes
* Time-consuming data preparation

This project addresses the problem by automating the **data extraction and consolidation process**.

---

## 🎯 Business Value

The solution provides:

* Automated financial data ingestion
* Centralized data consolidation
* Reduced manual data preparation
* Reusable ETL workflow
* Better reporting efficiency
* A centralized dataset for Power BI analysis
* Interactive financial reporting

---

## 🔍 Key Learning Outcomes

Through this project, I gained practical experience in:

* Python-based ETL
* Pandas data processing
* Google Drive API integration
* API authentication
* Working with multiple file formats
* Data consolidation
* Power BI dashboard development
* DAX calculations
* Business intelligence
* Financial data analysis

---

## 🔮 Future Improvements

Potential improvements include:

* Automated data-quality checks
* Missing-value handling
* Duplicate detection
* Data-type validation
* ETL logging
* Error monitoring
* Incremental data loading
* Automated scheduled execution
* Power BI dataset refresh automation
* Additional financial KPIs
* Advanced DAX calculations

---

## 👨‍💻 Author

**Kunal Singh**
- GitHub: https://github.com/Kunal-KT
- LinkedIn: https://www.linkedin.com/in/kunal0306/

Data Analyst | Python | SQL | Power BI | Pandas | DAX
