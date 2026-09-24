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
These queries form the foundation of the analysis:
## Q1️⃣ Count of patients by gender and their average obsession score  
<img width="434" height="188" alt="image" src="https://github.com/user-attachments/assets/0382fc77-0400-4868-9598-a3bdf76f126d" />

-----

## Q2️⃣ Calculate patient count and percentage by gender  
→ Measures demographic distribution and representation.

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



