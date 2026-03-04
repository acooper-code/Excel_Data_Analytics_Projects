# Excel Salary and Skill Analysis

## Introduction

This project was created to help job seekers investigate the top requested skills for their desired jobs, and understand which skills will land more pay. 

### Questions to Analyse

To understand the data science job market, I asked:

- **1️⃣ Do more skills get you better pay?**
- **2️⃣ What’s the salary for data jobs in different regions?**
- **3️⃣ What are the top skills of data professionals?**
- **4️⃣ What’s the pay for the top 10 skills?**

### Analysis File 

[1_Project_Analysis.xlsx](https://github.com/user-attachments/files/25740521/1_Project_Analysis.xlsx)

### Excel Skills Used 

- **ℹ️ Pivot Tables**
- **📊 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **❔ Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The data is from [Luke Barousse's Excel for Data Analytics](https://www.youtube.com/watch?v=pCJ15nGFgVg&t=38585s) course on YouTube. It contains detailed information on job titles, salaries, locations, and data science skills. 

## 1️⃣ Do more skills get you better pay?

### ❔ Power Query (Extract, Transform, Load)

- **Extract:** Utilised power query to extract the original data and create two queries; one containing all data jobs information, and one containing the skills for each job ID. 
- **Transform:** Transformed each query by formatting column types, removing unnecessary columns, cleaning text to eliminate unwanted information, trimming white space, and fixing formatting inconsistencies.

Applied steps for `data_jobs_all`:

<img width="244" height="312" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/7cbf10db-cbcd-4562-892d-73f1bdaf9714" />

Applied steps for `data_jobs_skills`:

<img width="243" height="328" alt="2_Project_Analysis_Screenshot2" src="https://github.com/user-attachments/assets/0b786b74-1c4c-4bca-9cb4-f05f8c151db7" />

- **Load:** I loaded both tranformed queries into my workbook, ready for analysis. 

Transformed data for `data_jobs_all`:

<img width="1916" height="649" alt="2_Project_Analysis_Screenshot3" src="https://github.com/user-attachments/assets/1a7b2d05-93f3-473f-a7f7-9d82cf4edf2a" />

Tranformed data for `data_jobs_skills`:

<img width="1914" height="702" alt="2_Project_Analysis_Screenshot4" src="https://github.com/user-attachments/assets/922a9164-bf97-405a-aa84-c9e84a0f56bb" />

### ℹ️ Pivot Tables and 📊 Pivot Charts (Analysis)

- **Pivot Tables** Calculated skills per job, and median salary for each job title. 
- **Pivot Charts:** Plotted skills per job against median salary, with data labels for job titles.

<img width="1908" height="1153" alt="Q1 Chart 1" src="https://github.com/user-attachments/assets/1f3fe1e7-c406-4612-a36f-ada7d7f9b1fd" />

- **Insights Gained:** There is a positive correlation between the number of skills requested in job postings and the median salary. Jobs requesting the most skills are Senior Data Engineer and Data Engineer. Jobs requesting the least skills are Business Analyst and Data Analyst. This suggests more specialised skill sets command more pay. However, Senior Data Scientist and Data Scientist jobs request less skills than Senior Data Engineer and Data Engineer respectively but are paid more, suggesting factors other than skill count influence data science salaries, such as depth of skills or greater decision impacts. This analysis highlights the value of acquiring mulitple relevant skills, particularly for job seekers aiming for higher-paying roles. 

## 2️⃣ What’s the salary for data jobs in different regions?

### ℹ️ Pivot Tables and 🧮 DAX

- **Pivot Tables:** Created a Pivot Table using the data model I created with Power Pivot. Moved job titles into rows, and average yearly salary into values. Added a new measure to calculate the median salary for United States jobs:

    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```
- **DAX:** Calculated median yearly salary using DAX: 

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

<img width="1776" height="738" alt="2_Project_Analysis_Chart2" src="https://github.com/user-attachments/assets/d987f8be-63eb-441d-b7bb-abd57c9dfe59" />

- **Insights Gained:** Jobs like Senior Data Engineer and Data Sceintist command higher median salaries in both the US and internationally, showing the global demand for high-level data expertise. The salary differences between US and Non-US data science jobs are most notable in high-tech jobs like Cloud Engineer and Machine Learning Engineer, which may reflect the high concentration of tech industries in the US. Understanding salary differences between roles and across locations helps professionals ensure they are being adequately compensated, and companies ensure they are in line with market standards.

## 3️⃣ What are the top skills of data professionals?

### 💪 Power Pivot 

- **Power Pivot:** Created a data model by integrating `data_jobs_all` and `data_jobs_skills` tables into one model. Refined my data model and created a measure for skill likelihood. 
- **Data Model:** Created a relationship between these two tables using the `job_id` column.

<img width="1788" height="1264" alt="2_Project_Analysis_Screenshot5" src="https://github.com/user-attachments/assets/b615dcfc-5f5e-4f9d-8c35-eb198c50e601" />

<img width="1662" height="1100" alt="Q2 chart 3" src="https://github.com/user-attachments/assets/c8ca12bc-6888-443c-a648-d953b771b85f" />

- **Insights Gained:** SQL and Python dominate as the most requested skills in data science jobs, reflecting their value as core skills in data processing and analysis. Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies. Understanding the top skills in the industry helps professionals stay competitive, and guides training and educational programmes within companies to focus on the most impactful technologies. 

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Pivot Charts

- **Design Choice:** Created a combo Pivot Chart to plot median salary and skill likelihood against median salary. Set primary axis as median salary in a clustured column format. Set secondary axis as skill likelihood in a line format with markers.
- **Data Organisation:** Removed the line of skill likelihood, leaving markers only, for improved readability. 

<img width="862" height="452" alt="2_Project_Analysis_Chart4" src="https://github.com/user-attachments/assets/e446fa3b-9ebd-46cf-a45c-0e5e29fe77a7" />

- **Insights Gained:** Higher median salaries are associatiated with skills like Python, Oracle, and SQL, suggesting their critical role in higher-paying tech jobs. Skills like Powerpoint and Word have the lowest median salaries and likelihood, suggesting less specialisation and demand in high-salary jobs. This chart highlights the value in learning high-value skills like Python and SQL, especially for job seekers looking to maximise their salary in the data science industry. 

## Conclusion

This project was created to provide users with specific insights into salary and skill trends across various data science roles. It enables job seekers to investigate the top requested skills for their desired jobs, and understand which skills will land more pay. 

The skills used to create this dahsboard I developed through following along with [Luke Barousse's Excel for Data Analytics](https://www.youtube.com/watch?v=pCJ15nGFgVg&t=38585s) course on YouTube.
