# Human Resource Analysis


### Project Overview
Based on the insights gathered from the Human Resource dataset, the project aims to provide a comprehensive overview of the company's workforce demographics, tenure, turnover rates, geographical distribution, job titles, and hiring trends. 

#### Data Visualization:

![Screenshot 2024-04-12 012449](https://github.com/Motjiang/Human-Resource_-Data-Analysis/assets/114883452/5e494334-6a76-48b1-a77a-a4630f0b681b)

![Screenshot 2024-04-12 012935](https://github.com/Motjiang/Human-Resource_-Data-Analysis/assets/114883452/e5503ddb-867e-41fe-be2d-102a1ef4d931)
### Data Sources
HR Data : This primary dataset used for this analysis is the "HR Data.csv" file, containg missing values.

### Tools
- Excel
- Microsoft Sql Server 2019
- Microsoft Power BI

### Data Preparation
- I performed the following tasks:
  
  1. Data loading & inspection  
  2. Handling missing values
  3. Handling null values
  4. Data cleaning and analysis
     


### Exploratory Data Analysis
- EDA involved exploring the HR data to answer the following key questions:
  
1.	How is the age spread within the company?
2.	What is the gender composition in the company?
3.	How does gender distribution differ across departments and job titles?
4.	What is the racial makeup of the company?
5.	What is the average duration of employment in the company?
6.	Which department experiences the most turnover?
7.	What is the tenure distribution across departments?
8.	How many employees in each department work remotely?
9.	What is the geographic distribution of employees across states?
10.	How are job titles distributed throughout the company?
11.	How have the number of hires fluctuated over time among employees?

### Data Analysis
- I used the following Subquery for age group distribution
```sql
SELECT
  age_group,
  COUNT(*) AS count
FROM (
  SELECT
    CASE
      WHEN age BETWEEN 21 AND 30 THEN '21 to 30'
      WHEN age BETWEEN 31 AND 40 THEN '31 to 40'
      WHEN age BETWEEN 41 AND 50 THEN '41-50'
      ELSE '50+'
    END AS age_group
  FROM [HR Data]
  WHERE new_termdate IS NULL
) AS Subquery
GROUP BY age_group
ORDER BY age_group;

```

### Findings
- The analysis findings are summarized as follows:
1. Male employees outnumber female and non-conforming employees within the company.
2. Gender representation is balanced across departments, with a slight predominance of male employees overall.
3. data shows that employees aged 31-40 constitute the largest portion of the workforce, followed closely by those aged 41-50. Employees aged 21-30 form the next significant portion, while employees aged 50 and above comprise the smallest demographic within the company.
4. Most employees in the company are Caucasian, followed by individuals of mixed race, black, Asian, Hispanic, and Native American backgrounds.
5. The average tenure of employment among employees is 7 years.
6. Auditing experiences the highest turnover rate, trailed by Legal, Research & Development, and Training departments. Conversely, Business Development & Marketing departments exhibit the lowest turnover rates.
7. Employees typically remain with the company for a duration spanning 6 to 8 years, with tenure evenly spread across departments.
8. Approximately 25% of employees work remotely.
9. The largest concentration of employees is in Ohio (14,788), followed by Pennsylvania (930), Illinois (730), Indiana (572), Michigan (569), Kentucky (375), and Wisconsin (321).
10. The company boasts a total of 182 job titles, with Research Assistant II employing the most individuals (634). Additionally, there are singular employees in roles such as Assistant Professor, Marketing Manager, Office Assistant IV, Associate Professor, and VP of Training and Development.
11. Over the years, there has been an increase in the number of employees hired by the company.

### Recommendations
1. Gender Diversity: Actively recruit more female and non-conforming employees to address the slight predominance of males.
2. Retention Focus: Implement retention strategies for high-turnover departments like Auditing, Legal, R&D, and Training.
3. Remote Work Policies: Refine remote work policies to support the 25% of employees working remotely.
4. Geographic Optimization: Tailor support and benefits to meet the needs of employees in Ohio, Pennsylvania, Illinois, Indiana, Michigan, Kentucky, and Wisconsin.
5. Career Progression Clarity: Clarify career paths across the company's 182 job titles to facilitate career advancement.
6. Long-Term Engagement: Invest in employee wellness, support, and growth opportunities to improve the average tenure of 7 years.









