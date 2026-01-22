# 🌍 AQI Index Analysis Dashboard | Power BI

An interactive **Power BI dashboard** analyzing **Air Quality Index (AQI)** data over a **10-year period**, designed to uncover pollution trends, dominant pollutants, and regional air quality severity across India.

This project focuses on **analytical accuracy, dynamic interactivity, and stakeholder-ready storytelling**, making it suitable for **environmental analytics, ESG reporting, and public policy insights**.

---

## 📌 Project Overview

Air pollution is a critical environmental and public health issue. This project analyzes historical AQI data to:

- Track **long-term AQI trends**
- Identify **high-risk regions and cities**
- Determine **dominant pollutants**
- Classify AQI severity using **standard thresholds**
- Enable **interactive, filter-driven exploration**

The dashboard allows users to slice data by **Year, State, and Area**, with all KPIs and visuals responding dynamically.

---

## 🗂️ Dataset Summary

- **Granularity:** Daily AQI observations  
- **Geography:** State, City, Area  
- **Metrics:** AQI value, AQI category, prominent pollutant  
- **Time Span:** ~10 years  

> ⚠️ Note: Only a **sample dataset** is included in this repository for demonstration purposes.

---

## 🧱 Data Modeling

- Created a **separate Calendar table** for time intelligence
- Established a **one-to-many relationship** between:
  - Calendar Date → AQI fact table
- Used **measures instead of calculated columns** to ensure:
  - Better performance
  - Accurate filter context
  - Scalable design

---

## 📊 Dashboard Features

### 🔹 KPI Indicators
- **Average AQI** (Gauge)
- **Maximum AQI** (Card)
- **Primary Pollutant**
  - Identifies pollutant(s) with highest occurrence using frequency-based DAX
- **AQI Category**
  - Derived dynamically from average AQI

---

### 🔹 AQI Categorization Logic

AQI levels are classified using standard thresholds:

| Category | AQI Range |
|--------|-----------|
| Good | 0 – 50 |
| Moderate | 51 – 100 |
| Poor | 101 – 150 |
| Unhealthy | 151 – 200 |
| Very Unhealthy | 201 – 300 |
| Hazardous | 301 – 500 |

Consistent color coding is applied across all visuals to improve interpretability.

---

### 🗺️ Geospatial Analysis
- Interactive map showing AQI levels across regions
- **Bubble size:** Average AQI  
- **Bubble color:** AQI category  
- Optimized aggregation to handle long time spans efficiently

---

### 📈 Trend Analysis
- Area chart visualizing **AQI trends over time**
- Separate **Year and Month slicers**
- Controlled visual interactions to isolate trend behavior without cross-filter noise

---

### 🏙️ City & Pollutant Insights
- **Top 10 cities** by average AQI (ranked bar chart with gradient coloring)
- **AQI level distribution** using a donut chart
- **Pollutant occurrence frequency** highlighting dominant pollutants such as PM2.5

---

## 🎛️ Interactivity
- Slicers for:
  - Year
  - State
  - Area (multi-select with Select All)
- Dynamic labels reflecting current filter context
- Responsive KPIs and visuals

---

## 🛠️ Tools & Technologies
- **Power BI**
- **DAX**
- Data Modeling & Time Intelligence
- Geospatial Visualization
- Dashboard UI/UX Design

---

## 🧠 Key Insights
- Persistent dominance of **PM2.5** as a primary pollutant
- High concentration of **Very Unhealthy AQI levels** in urban regions
- Clear seasonal and temporal AQI fluctuations
- Significant variation in pollution severity across cities and states

---

## 📂 Repository Structure

