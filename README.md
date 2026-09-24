 ### Healthcare-Data-Analysis-OCD-Patient-Insights-MySQL-Project-🩺
SQL‑based healthcare data analysis project exploring OCD patient demographics, symptom patterns, and treatment insights using MySQL queries and data documentation

## Objective🎯
This project explores clinical and behavioral patterns among patients diagnosed with Obsessive‑Compulsive Disorder (OCD) using SQL queries. The goal is to analyze demographic trends, symptom severity, and common obsession/compulsion types to uncover meaningful insights for healthcare decision‑making.

 #### Dataset Overview📊
The dataset includes anonymized patient records with attributes such as:
Demographics: Age, Gender, Ethnicity, Marital Status, Education Level
Clinical Data: OCD Diagnosis Date, Duration of Symptoms, Previous Diagnoses, Family History of OCD
Behavioral Metrics: Obsession Type, Compulsion Type, Y‑BOCS Scores (Obsessions & Compulsions)
Comorbidities & Treatment: Depression/Anxiety Diagnosis, Medications


 ### Data Dictionary📘 
 <img width="530" height="290" alt="image" src="https://github.com/user-attachments/assets/53991a46-c0a0-4639-858e-55075b5bef0d" />
<img width="548" height="296" alt="image" src="https://github.com/user-attachments/assets/717d32b3-1bdf-403c-8d82-0261b2c6c757" />


 ## Analytical Questions & SQL Approach 🧠
### Q1 Count of patients by gender and their average obsession score  
```sql
select count(*) total_patient,gender,
round(avg(`Y-BOCS Score (Obsessions)`),2) avg_score_obs
 from health.care
 group by gender;
 ----the  avg_score_obs is 20.20 per 'female' and 19.90 per 'male'
 
-----

### Q2 Calculate patient count and percentage by gender 
 with CTE_TOTAL_GENDER AS
 ( 
	select count(*) total_pat,gender,
round(avg(`Y-BOCS Score (Obsessions)`),2) avg_score_obs
 from health.care
 group by gender)
 ,TOTAL_PATIENTS
 AS (
 SELECT SUM(total_pat) TOTAL
 FROM CTE_TOTAL_GENDER)
 SELECT g.total_pat,
 g.gender,
 g.avg_score_obs,
 round((total_pat/t.total)*100,2) percentg
 from TOTAL_PATIENTS t
 join CTE_TOTAL_GENDER g;
-- PERCENTAGE IS 49.80% PER FEMALE , 50.20% PER MALE
--------------

## Q3️⃣ Count of patients month‑over‑month (MOM)  
→ Tracks diagnosis trends over time to identify seasonal or yearly patterns.

## Q4️⃣ Find the most common obsession type and its average score  
→ Highlights dominant OCD manifestations and their intensity.

## Q5️⃣ Find the most common compulsion type and its average compulsion score  
→ Identifies behavioral patterns and severity levels across patients.

First 2 queries was executed using CTEs (Common Table Expressions) for clarity and modular analysis.




## Tools & Techniques 🧩
MySQL Workbench — data cleaning, querying, and aggregation
SQL Functions: COUNT(), AVG(), ROUND(), GROUP BY, CTE, and date functions
Data Export: .sql dump for reproducibility and GitHub documentation

 ## Key Insights (examples) 💡
Female patients show slightly higher average obsession scores.
Harm‑related and contamination obsessions are the most frequent types.
SSRIs are the most common medication among patients with anxiety comorbidity.
Diagnosis frequency increased steadily over recent years.



