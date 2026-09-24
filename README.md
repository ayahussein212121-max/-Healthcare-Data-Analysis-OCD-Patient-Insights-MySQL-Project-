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
```SQL2
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
----- PERCENTAGE IS 49.80% PER FEMALE , 50.20% PER MALE

--------------

## Q2 Count of patients month‑over‑month (MOM)
SET SQL_SAFE_UPDATES=0;
 
update health.care 
set `OCD Diagnosis Date`=str_to_date(`OCD Diagnosis Date`,'%m/%d/%Y')
where str_to_date(`OCD Diagnosis Date`,'%m/%d/%Y') is not null ;

alter table health.care 
modify column `OCD Diagnosis Date`date;
select
count(*) patient_count,
date_format(`OCD Diagnosis Date`,'%Y-%m-01 00:00:00') month
from health.care 
group by month
order by month ;

## Q4 Find the most common obsession type and its average score  
select `Obsession Type`,
count(*) total_pat,
round(avg(`Y-BOCS Score (Obsessions)`),2) avg_score
from health.care
group by `Obsession Type`
order by total_pat
limit 1;
---------------------------------

## Q5️ Find the most common compulsion type and its average compulsion score  
select `Compulsion Type`,
count(*) total_pat,
round(avg(`Y-BOCS Score (Compulsions)`),2) avg_score
from health.care
group by 1
order by 2 
limit 1;

----------------------------------------
First 2 queries was executed using CTEs (Common Table Expressions) for clarity and modular analysis.

----------------------------------------------


## Tools & Techniques 🧩
MySQL Workbench — data cleaning, querying, and aggregation
SQL Functions: COUNT(), AVG(), ROUND(), GROUP BY, CTE, and date functions
Data Export: .sql dump for reproducibility and GitHub documentation

 ## Key Insights💡
1- Female patients show a slightly higher average obsession score (20.20) compared to males (19.90).
➡️ Insight: Gender may play a role in OCD symptom severity, with females experiencing marginally stronger obsessive symptoms
2-Patient distribution is nearly balanced: 49.8% female vs. 50.2% male.
➡️ Insight: OCD prevalence is evenly spread across genders, making differences in severity more clinically relevant than raw counts
3-Patient counts vary across months, showing fluctuations in diagnosis frequency.
➡️ Insight: Tracking diagnosis trends over time may reveal external triggers such as stress cycles, academic/work seasons, or environmental factors
4-The most frequent obsession type is Contamination, with the highest patient count and notable average severity scores.
➡️ Insight: Contamination fears are the dominant OCD manifestation, consistent with clinical literature
5-The most frequent compulsion type is Washing, with strong average compulsion scores.
➡️ Insight: This reinforces the link between contamination obsessions and washing compulsions — a classic OCD pattern.
