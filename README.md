# Global AI Content Impact: Hype & Fatigue Tracker

## 📌 Project Overview
This project is an advanced business intelligence and data science portfolio piece designed to track a critical behavioral anomaly: the expanding gap between skyrocketing AI-generated content volume and falling consumer trust. Built using Power BI Desktop, this dashboard functions as a high-visibility "Situational Command Center" to evaluate which global industries are facing the most severe public backlash relative to their automation levels.

The dashboard layout, structural flow, and design logic were implemented following the framework outlined in the **power bi project guide.pdf**. The final, production-ready dashboard is saved in this repository as **power bi project.pbix**.

### 📊 Live Dashboard Preview
*(Pro-Tip: Replace this text with a crisp screenshot of your final dark mode dashboard or an animated GIF of the dashboard in action!)*

---

## 🛠️ Data Architecture & Modeling
Rather than using a single, flat source table, this project adheres to strict relational database normalization standards to demonstrate Star Schema architectural skills. 

Using the Power Query Editor, the core dataset (`Global_AI_Content_Impact_Dataset.csv`) was deconstructed into a central Fact table and two distinct Dimension tables to establish a clean 1:N relationship mapping:

*   **Fact Table:** `Global_AI_Content_Impact_Dataset` — Contains primary numeric metrics, timelines, and transactional records.
*   **Dim_Country:** Contains unique country lists mapped to generated `Country ID` integer keys to enable seamless filtering.
*   **Dim_Industry:** Contains unique industry classifications mapped to custom `IndustryID` keys, eliminating redundant text fields from the main fact table.

---

## 📐 Engineered DAX Measures
Advanced Data Analysis Expressions (DAX) were engineered to calculate behavioral anomalies, shifting away from standard, unadjusted data summaries:

### 1. Total AI Generation Volume (TBs)
```dax
Total_AI_Volume_TBs = 
SUM('Global_AI_Content_Impact_Dataset'[AI-Generated Content Volume (TBs per year)])
