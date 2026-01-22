# 📊 Dataset Description

This folder contains the **cleaned and analysis-ready dataset** used for the AQI Power BI dashboard.

## File Included
- `aqi_cleaned.csv`

This CSV was **directly loaded into Power BI** and used as the primary fact table for all visuals and measures.

---

## 🧹 Data Cleaning & Preparation

All data preparation steps were performed either:
- Prior to loading the file, or
- Inside **Power BI (Power Query)**

Key cleaning steps include:
- Removal of invalid and null AQI values
- Standardization of pollutant names
- Consistent AQI category labeling
- Date formatting for time intelligence
- Geographic field normalization (State, City, Area)

---

## 🧱 Data Structure

The dataset contains:
- **Date** (daily granularity)
- **Geographic attributes** (State, City, Area)
- **AQI value**
- **AQI Category**
- **Prominent Pollutant**

A separate **Calendar table** was created within Power BI for time-based analysis.

---

## ℹ️ Notes

- Only the cleaned dataset is included to keep the repository concise and focused.
- Raw data is excluded intentionally to avoid redundancy and licensing concerns.
- The provided dataset is sufficient to reproduce the Power BI dashboard.

---

## 🔐 Disclaimer
This dataset is shared for **educational and portfolio purposes only**.
