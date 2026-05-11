# 🚀 AI, ML & Data Jobs Dashboard

An end-to-end **Power BI Dashboard Project** focused on analyzing AI, Machine Learning, and Data-related job trends across different countries, companies, experience levels, industries, and work modes.

This project demonstrates the complete analytics workflow — from **data cleaning and modeling** to **DAX calculations, interactive dashboards, and business insights generation**.

---

# 📌 Project Overview

The dashboard provides insights into:

- 📈 Job trends over time
- 🌍 Location-based hiring analysis
- 💼 Company & role insights
- 🧠 Skill demand analysis
- 💰 Salary analysis by country & experience
- 🏠 Remote vs On-site work trends
- 👨‍💻 Employment type distribution

---

# 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Power BI | Dashboard Development |
| Power Query | Data Cleaning & Transformation |
| DAX | Measures & Calculations |
| Star Schema Modeling | Data Modeling |
| Microsoft Fabric | Dashboard Publishing |

---

# 📂 Project Workflow

## 1️⃣ Data Cleaning (ETL Process)

Performed data cleaning using Power Query:

- Removed null and duplicate values
- Standardized columns
- Handled inconsistent data
- Formatted dates and salary columns
- Prepared datasets for modeling

---

## 2️⃣ Data Modeling

Implemented a **Star Schema** model for optimized performance and better relationships.

### Fact Table
- `Fact_Jobs`
- `Fact_Job_Skills`

### Dimension Tables
- `Dim_Companies`
- `Dim_Locations`
- `Dim_Skills`
- `Dim_Date`

---

# 📊 Key Dashboard Insights

## 🔹 AI, ML & Data Jobs Overview
- Total jobs
- Average salary
- Median salary
- Remote job percentage
- Experience-wise hiring trends

## 🔹 Location Insights
- Country-wise job distribution
- Region-wise salary analysis
- Work mode by country
- Employment distribution across countries

## 🔹 Company & Role Insights
- Company rating comparison
- Experience-level hiring patterns
- Job roles vs work modes
- Remote ratio analysis

## 🔹 Skill & Hiring Insights
- Skill usage by experience level
- Industry-wise skill demand
- Salary trends by seniority
- Most in-demand skills

---

# 📈 Important DAX Measures

## Average Salary

```DAX
AvgSalary =
VAR AvgSal = AVERAGE(Fact_Jobs[Salary_USD])
RETURN
IF(
    ISBLANK(AvgSal),
    0,
    AvgSal
)
```

---

## Average Salary by Country

```DAX
AvgSalaryByCountry =
VAR AvgSal =
    AVERAGEX(
        VALUES(Dim_Locations[Country]),
        CALCULATE([AvgSalary])
    )
RETURN
IF(
    ISBLANK(AvgSal),
    0,
    AvgSal
)
```

---

## Average Salary by Experience

```DAX
AvgSalaryByExperience =
VAR AvgSal =
    AVERAGEX(
        VALUES(Fact_Jobs[Experience_Level]),
        CALCULATE([AvgSalary])
    )
RETURN
IF(
    ISBLANK(AvgSal),
    0,
    AvgSal
)
```

---

## Previous Month Jobs

```DAX
PreviousMonthJob =
VAR PrevJob =
    CALCULATE(
        [TotalJobs],
        PREVIOUSMONTH(Dim_Date[Date])
    )
RETURN
IF(
    ISBLANK(PrevJob),
    0,
    PrevJob
)
```

---

## Month-over-Month Job Growth %

```DAX
JobsMOM% =
COALESCE(
    DIVIDE(
        [TotalJobs] - [PreviousMonthJob],
        [PreviousMonthJob],
        0
    ) * 100,
    0
)
```

---

# 🎨 Dashboard Features

✅ Interactive dashboards  
✅ KPI cards  
✅ Advanced visuals  
✅ Map visualizations  
✅ Dynamic filtering & slicing  
✅ Responsive report formatting  
✅ Business-focused storytelling  

---

# 📷 Dashboard Preview

## AI, ML & Data Jobs Overview
(![Dashboard Image 1](Images/image%201.png))

## Location Insights
(Add Screenshot Here)

## Company & Role Insights
(Add Screenshot Here)

## Skill & Hiring Insights
(Add Screenshot Here)

---

# 🧠 Key Learnings

Through this project, I learned:

- Real-world Power BI workflow
- Building Star Schema models
- Writing optimized DAX measures
- Designing interactive dashboards
- Creating business-driven insights
- Dashboard storytelling techniques

---

# 🚀 Future Plans

- More advanced Power BI dashboard projects
- SQL integration projects
- Real-world analytics case studies
- Advanced DAX optimization

---

# 📬 Connect With Me

## LinkedIn
(https://www.linkedin.com/in/pranay-jha-6582a937b/)

---

# ⭐ If you liked this project

Give this repository a ⭐ and feel free to share feedback or suggestions!

---
