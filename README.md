# Excel Data Science Projects

## 📁 Table of Contents

- [Project 1: Excel Salary Dashboard](#project-1-excel-salary-dashboard)
  - [Introduction](#introduction)
  - [Excel Skills I Used](#excel-skills-i-used)
  - [How I Built the Dashboard](#how-i-built-the-dashboard)
    - [Charts](#-charts)
    - [Formulas and Functions](#-formulas-and-functions-i-built)
    - [Data Validation](#-data-validation-i-implemented)
  - [Conclusion](#conclusion)

- [Project 2: Data Science Job Market Analysis](#project-2-data-science-job-market-analysis)
  - [Introduction](#introduction-1)
  - [Excel Skills I Used](#excel-skills-i-used-1)
  - [Do more skills get you better pay?](#1️⃣-do-more-skills-get-you-better-pay)
  - [Salary for data jobs in different regions?](#2️⃣-whats-the-salary-for-data-jobs-in-different-regions)
  - [Top skills of data professionals?](#3️⃣-what-are-the-top-skills-of-data-professionals)
  - [Pay for the top 10 skills?](#4️⃣-whats-the-pay-of-the-top-10-skills)
  - [Conclusion](#conclusion-1)

---

# Project 1: Excel Salary Dashboard

![1_Salary_Dashboard.png](/Data/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

I built this data jobs salary dashboard to help job seekers — including myself — investigate salaries for desired roles and ensure fair compensation.

The data comes from my Excel course, which gave me a strong foundation in analyzing data using this powerful tool. I worked with detailed information on job titles, salaries, locations, and essential skills, all of which are presented in this dashboard.

### Dashboard File
My final dashboard is in [Salary_Insights_Dashboard.xlsx](Salary_Insights_Dashboard.xlsx).

### Excel Skills I Used

Here are the Excel skills I applied throughout this project:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset I used contains real-world data science job information from 2023, sourced via my Excel course. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

---

## How I Built the Dashboard

### 📉 Charts

#### 📊 Data Science Job Salaries — Bar Chart

<img src="../Data/Images/1_Salary_Dashboard_Chart1.png" width="900" height="500" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features I Used:** I used the bar chart feature with formatted salary values and optimized the layout for clarity.
- 🎨 **My Design Choice:** I chose a horizontal bar chart to make median salary comparisons easy to scan visually.
- 📉 **How I Organized the Data:** I sorted job titles by descending salary to improve readability at a glance.
- 💡 **What I Found:** This chart made it easy to spot salary trends — Senior roles and Engineers consistently out-earn Analyst roles.

#### 🗺️ Country Median Salaries — Map Chart

![1_Salary_Dashboard_Chart2.png](/Data/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features I Used:** I leveraged Excel's map chart feature to plot median salaries across the globe.
- 🎨 **My Design Choice:** I used a color-coded map to visually differentiate salary levels across regions at a glance.
- 📊 **How I Represented the Data:** I plotted the median salary for each country where data was available.
- 👁️ **Visual Enhancement:** This approach dramatically improved readability and made geographic salary trends immediately apparent.
- 💡 **What I Found:** The map quickly revealed global salary disparities and highlighted which regions pay the most and least.

---

### 🧮 Formulas and Functions I Built

#### 💰 Median Salary by Job Title
```excel
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** I set up the formula to check job title, country, and schedule type simultaneously, while also excluding blank salary entries.
- 📊 **Array Formula:** I nested an `IF()` statement inside `MEDIAN()` to evaluate the full data array in one go.
- 🎯 **Tailored Insights:** This gives me — and other users — salary data specific to a chosen job title, region, and work type.
- **🔢 What It Does:** This formula populates the background table below, returning the median salary based on the job title, country, and type selected.

🍽️ Background Table

![1_Salary_Dashboard_Screenshot1.png](/Data/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="/Data/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

---

#### ⏰ Count of Job Schedule Type
```excel
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** I used the `FILTER()` function to exclude entries containing "and" or commas, and to drop any zero values — keeping only clean, distinct schedule types.
- **🔢 What It Does:** This formula populates the table below with a clean list of unique job schedule types for use in the dashboard filters.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/Data/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation

<img src="../Data/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

---

### ❎ Data Validation I Implemented

#### 🔍 Filtered List

- 🔒 **How I Enhanced Data Validation:** I applied the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` fields via the Data tab. This ensures:
    - 🎯 User input is restricted to predefined, validated options only
    - 🚫 Incorrect or inconsistent entries are blocked before they can cause issues
    - 👥 The overall usability and reliability of the dashboard is improved

<img src="../Data/Images/1_salary_dashboard_data_validation.gif" width="425">

---

## Conclusion

I created this dashboard to showcase real insights into salary trends across various data-related job roles. Using data from my Excel course, I built a tool that helps users — and myself — make more informed decisions about career paths. The dashboard lets you explore how location and job type influence compensation, all in one place.

---
---

# Project 2: Data Science Job Market Analysis

## Introduction

As a job seeker, I've always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.

### Questions I Wanted to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What's the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What's the pay for the top 10 skills?**

### Excel Skills I Used

Here are the Excel skills I applied throughout this project:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset I used contains real-world data science job information from 2023, sourced via my Excel course. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

---

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill I Used: Power Query (ETL)

#### 📥 Extract

I started by using Power Query to extract the original data (`data_salary_all.xlsx`) and created two queries:
- 🗃️ The first containing all data jobs information.
- 🔧 The second listing the skills associated with each job ID.

#### 🔄 Transform

I then transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.

- 📊 data_jobs_all

    ![2_Project_Analysis_Screenshot1.png](/Data/Images/2_Project_Analysis_Screenshot1.png)

- 🛠️ data_job_skills

    ![2_Project_Analysis_Screenshot2.png](/Data/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.

- 📊 data_jobs_all

    ![2_Project_Analysis_Screenshot3.png](/Data/Images/2_Project_Analysis_Screenshot3.png)

- 🛠️ data_job_skills

    ![2_Project_Analysis_Screenshot4.png](/Data/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights

- 📈 I found a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries — suggesting that more specialized skill sets command higher market value.

    ![2_Project_Analysis_Chart1.png](/Data/Images/2_Project_Analysis_Chart1.png)

#### 🤔 So What

This trend reinforced for me the value of acquiring multiple relevant skills, especially for anyone aiming for higher-paying roles.

---

## 2️⃣ What's the salary for data jobs in different regions?

### 🧮 Skills I Used: PivotTables & DAX

#### 📈 Pivot Table

- 🔢 I created a PivotTable using the Data Model I built with Power Pivot.
- 📊 I moved `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 I then added a new measure to calculate the median salary specifically for United States jobs:
```
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States")
```

#### 🧮 DAX

To calculate the overall median year salary, I used the following DAX measure:
```
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
```

### 📊 Analysis

#### 💡 Insights

- 💼 I found that roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary gap between US and Non-US roles is especially notable in high-tech jobs, likely influenced by the concentration of tech industries in the US.

    ![2_Project_Analysis_Chart2.png](/Data/Images/2_Project_Analysis_Chart2.png)

#### 🤔 So What

These salary insights are valuable for career planning and salary negotiations — helping professionals and companies align their offers with market standards while accounting for geographic differences.

---

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill I Used: Power Pivot

#### 💪 Power Pivot

- 🔗 I built a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into a single model.
- 🧹 Since I had already cleaned the data using Power Query, Power Pivot was able to automatically establish a relationship between the two tables.

#### 🔗 Data Model

I created the relationship between the two tables using the `job_id` column.

![2_Project_Analysis_Screenshot5.png](/Data/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

I used the Power Pivot menu to refine my data model and create measures efficiently.

![2_Project_Analysis_Screenshot6.png](/Data/Images/2_Project_Analysis_Screenshot6.png)

### 📊 Analysis

#### 💡 Insights

- 💻 I found that SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, highlighting the industry's ongoing shift toward cloud services and big data.

    ![2_Project_Analysis_Chart3.png](/Data/Images/2_Project_Analysis_Chart3.png)

#### 🤔 So What

Understanding which skills are most prevalent not only helps professionals stay competitive, but also informed my own learning priorities going forward.

---

## 4️⃣ What's the pay of the top 10 skills?

### 📊 Skill I Used: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable:
- 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
- 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)

To polish the chart, I added an axis title, removed the skill likelihood lines, and changed the markers to diamonds.

### 📊 Analysis

#### 💡 Insights

- 💰 I observed that higher median salaries are associated with skills like Python, Oracle, and SQL — confirming their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word sit at the bottom for both median salary and likelihood, indicating less specialization and lower demand in high-salary sectors.

    ![2_Project_Analysis_Chart4.png](/Data/Images/2_Project_Analysis_Chart4.png)

#### 🤔 So What

This chart reinforced my belief in investing time in high-value skills like Python and SQL — they are clearly tied to higher-paying roles for anyone looking to maximize their earnings in tech.

---

## Conclusion

As a data enthusiast and former job seeker, I took on this Excel-based project to uncover meaningful insights about the data science job market. Using a dataset I curated from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Power Query, PivotTables, DAX, and advanced charts, I discovered key correlations between having multiple skills and earning higher salaries — particularly with Python, SQL, and cloud technologies.

I hope this project serves as a practical guide for fellow data professionals and sheds light on the skills most worth pursuing for higher-paying roles.