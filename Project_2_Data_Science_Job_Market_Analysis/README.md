# Data Science Job Market Analysis

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