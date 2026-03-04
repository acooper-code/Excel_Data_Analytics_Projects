# Excel Salary Dashboard

![1_Salary_Dashboard_Final_Dashboard](https://github.com/user-attachments/assets/7b75cc67-7f3d-4f51-95e4-3659d57c1138)

## Introduction

This interactive salary dashboard was created to help job seekers investigate salaries for their desired jobs, and ensure they are being adequately compensated. 

### Dashboard File
[1_Salary_Dashboard.xlsx](https://github.com/user-attachments/files/25738060/1_Salary_Dashboard.xlsx)

### Excel Skills Used

- **🧮 Formulas and Functions**
- **✅ Data Validation**
- **📊 Charts**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The data is from [Luke Barousse's Excel for Data Analytics](https://www.youtube.com/watch?v=pCJ15nGFgVg&t=38585s) course on YouTube. It contains detailed information on job titles, salaries, locations, and data science skills. 

## Dashboard Build

### 🧮 Formulas and Functions

#### Median Salary with Multi-Criteria Filtering

```
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
- **Formula Purpose:** Checks job title, country, and schedule type, then calculates median salary for specified roles, excluding blank values.

<img width="265" height="220" alt="1_Salary_Dashboard_Screenshot1" src="https://github.com/user-attachments/assets/fba9cf6e-fbc4-430d-8687-8ab61c5c91d9" />

- **Key Functions:** Utilises `MEDIAN()` and `IF()` functions to analyse an array.
- **Use within Dashboard:** Provides user with specific salary information for selected job title, country, and schedule type. 

<img width="1148" height="1214" alt="1_Salary_Dashboard_Job_Title" src="https://github.com/user-attachments/assets/87917867-447e-4c60-9c72-9062bb5c031f" />

#### Unique Schedule Type List

```
=FILTER(J2#,(
NOT(
ISNUMBER(
SEARCH("and",J2#)
)*(J2#<>0)
)
```
- **Formula Purpose:** Searches for schedule type data containing mulitple values (those containing the word "and"), and filters them out, along with blank values.

<img width="195" height="119" alt="1_Salary_Dashboard_Screenshot2" src="https://github.com/user-attachments/assets/c6c42aa8-f957-4168-8f7c-20fb4ca7c8c6" />

- **Key Functions:** Utilises `SEARCH()` and `FILTER()` functions to remove undesired data from an array.
- **Use within Dashboard:** Provides a list of unique schedule types for the user to select from.

<img width="942" height="1212" alt="1_Salary_Dashboard_Type" src="https://github.com/user-attachments/assets/d0557bb3-7bf9-4e6b-9e13-f9f4944aed9f" />

### ✅ Data Validation

#### Filtered List

![1_Salary_Dashboard_Data_Validation](https://github.com/user-attachments/assets/859ad41f-b92a-4edc-b25f-fc1eb634fe17)

- **Data Validation Purpose:** Implements filtered lists for job title, country, and schedule type selection, restricting user selection to predefinied, validated values.  
- **Use Within Dashboard:** Improves the overall usability of the dashboard by preventing incorrect or inconsistent user entries, removing blank and duplicate values from the lists. 

### 📊 Charts

#### Data Science Job Median Salaries - Bar Chart

<img width="1336" height="867" alt="1_Salary_Dashboard_Chart1" src="https://github.com/user-attachments/assets/4bcf0d50-9156-424e-a0ae-5c43400a550b" />

- **Design Choice:** Utilised bar chart feature to horizontally display median salary values for each job title. 
- **Data Organisation:** Formatted median salary axis values, and sorted job titles by descending median salaries for improved readability. 
- **Insights Gained:** Enables quick identification of salary trends by job title. 

#### Country Median Salaries - Map Chart

![1_Salary_Dashboard_Country_Map](https://github.com/user-attachments/assets/d7aa93fb-4ffe-437e-bd50-0b7a3addcf49)

- **Design Choice:** Utilised map chart feature to display median salary values by country globally. 
- **Data Organisation:** Colour-coded map differentiates between areas of high and low median salary values. 
- **Insight Gained:** Enables immediate understanding of geographic salary trends. 

## Conclusion

I created this interactive salary dashboard to provide users with specific insights into salary trends across various data science roles and regions. Using this dashboard allows job seekers to investigate salaries for their desired jobs, and ensure they are being adequately compensated. 

The skills used to create this dahsboard I developed through following along with [Luke Barousse's Excel for Data Analytics](https://www.youtube.com/watch?v=pCJ15nGFgVg&t=38585s) course on YouTube.
