# Introduction

While searching for jobs in the data field, I noticed something missing: there’s surprisingly little structured data that reveals which skills employers value most and how those skills translate into pay. This inspired me to dig into the data science job market and uncover patterns around skills, salaries, and demand. My goal was simple — to understand what employers really want and how these requirements connect to earning potential.

## Key Questions Explored

To guide the analysis, I focused on:

* *Does having more skills lead to higher salaries?*
* *How do salaries differ across regions?*
* *Which skills are most in demand among data professionals?*
* *What’s the pay for the top 10 most sought-after skills?*

## Tools & Skills Used

Throughout the project, I relied on the following Excel capabilities:

* **Pivot Tables** for summarizing and grouping data.
* **Pivot Charts** for visualizing trends and comparisons.
* **DAX (Data Analysis Expressions)** to calculate custom metrics like median salary.
* **Power Query** for extracting and cleaning raw data.
* **Power Pivot** to build a relational data model for deeper analysis.

## Dataset

The dataset contained real-world data science job postings from 2023, including:

* **Job Titles**
* **Annual Salaries**
* **Geographic Locations**
* **Required Skills**

### 1. Do More Skills Mean Better Pay?
**Skill Focus:** Power Query (ETL)

**Process:**

* Extract: Used Power Query to import the dataset (data_salary_all.xlsx) and create two queries — one for overall job details and another listing skills per job ID.

* Transform: Adjusted data types, removed unnecessary columns, standardized text, and trimmed extra spaces.

*data_job_salary*
![Data job salary applied settings](../Images/Project_Analysis_Screenshot-4.png)

*data_job_skills*
![Data job skills applied settings](../Images/Project_Analysis_Screenshot-5.png)

* Load: Brought the cleaned tables (data_jobs_all and data_job_skills) into Excel for analysis.

*data_job_salary*
![data job salary-Power Query ETL](../Images/Power Query ETL-2.png)

*data_job_skills*
![Data job skils Power Query ETL](../Images/Power Query ETL-3.png)

**Findings:**

* Roles such as Senior Data Engineer and Data Scientist often require multiple skills and correspond with higher median salaries.

* Roles with fewer required skills, like Business Analyst, generally have lower pay.

![Salary Analysis](../Images/Salary-Analysis.png)

**Takeaway:**
Building a diverse skill set can significantly improve earning potential, especially in technical and specialized positions.

### 2. How Do Salaries Vary by Region?
**Skill Used:** PivotTables & DAX

**Process:**

* Created a PivotTable from the Power Pivot data model.

* Added a DAX measure to calculate the median annual salary for US-based jobs:

##### DAX
```
Median Salary :=
MEDIAN(data_jobs_all[salary_year_avg])
```

**Findings:**

* Senior-level technical roles have high median salaries both in the US and abroad.

* The US shows a particularly strong salary premium in tech-heavy positions, likely due to industry concentration.

![Pivot Tables & DAX](../Images/Project_Analysis_Chart2.png)

**Takeaway:**
Salary expectations should factor in both the role and location — geographic differences can heavily influence pay.

### 3. What Are the Top Skills for Data Professionals?
**Skill Focus:** Power Pivot

**Process:**

* Linked data_jobs_all and data_job_skills via the job_id column in Power Pivot.

![Relationship Diagram](../Images/Project_Analysis_Screenshot-1.png)

* Used the data model to identify skill frequency across job postings.

![Power Pivot](../Images/Project_Analysis_Screenshot-2.png)

**Findings:**

* SQL and Python dominate as essential skills.

* Cloud tools like AWS and Azure are becoming increasingly relevant in the market.

![Horizontal Bar Chart](../Images/Project_Analysis_Chart3.png)

**Takeaway:**
Staying competitive means mastering core programming languages while keeping up with emerging cloud technologies.

### 4. What’s the Pay for the Top 10 Skills?
**Skill Focus:** Pivot Chart (Combo Chart)

**Process:**

* Created a combination PivotChart to display both median salary and skill likelihood (%).

* Used a clustered column for salary and a line chart with markers for skill likelihood.

**Findings:**

* Skills like Python, Oracle, and SQL are linked to the highest median salaries.

* General tools like PowerPoint and Word appear far less often and are tied to lower salaries.

![Bar chart with line chart](../Images/Project_Analysis_Chart4.png)

**Takeaway:**
If salary growth is a priority, focus on mastering technical skills with high market demand.

# Conclusion

This project was my opportunity to explore the data science job market through a hands-on Excel analysis. By leveraging Power Query, Power Pivot, PivotTables, DAX, and charting tools, I uncovered a clear link between specialized skills and higher salaries.

For aspiring data professionals, the message is clear:

* Learn multiple in-demand skills.

* Pay attention to geographic pay differences.

* Focus on technical capabilities that employers consistently value.

While the dataset was originally sourced from Luke Barousse’s Excel for Data Analytics tutorial, I adapted the process to my own style of analysis, applying my personal workflow and insights.
