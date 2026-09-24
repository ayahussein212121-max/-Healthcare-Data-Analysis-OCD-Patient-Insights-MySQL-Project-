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

Column Name	Description	Data Type
patient_id	Unique identifier for each patient	Integer
age	Patient’s age in years	Integer
gender	Gender of the patient (Male/Female)	Text
ethnicity	Ethnic background of the patient	Text
marital_status	Marital status (Single, Married, Divorced, etc.)	Text
education_level	Highest education level attained	Text
ocd_diagnosis_date	Date of OCD diagnosis	Date
duration_of_symptoms_months	Duration of OCD symptoms in months	Integer
previous_diagnoses	Other mental health conditions previously diagnosed (e.g., MDD, PTSD, GAD)	Text
family_history_of_ocd	Indicates if OCD runs in the family (Yes/No)	Text
obsession_type	Type of obsession (e.g., Harm‑related, Contamination, Symmetry, Hoarding)	Text
compulsion_type	Type of compulsion (e.g., Checking, Washing, Ordering, Praying)	Text
y_bocs_score_obsessions	Y‑BOCS score measuring obsession severity	Integer
y_bocs_score_compulsions	Y‑BOCS score measuring compulsion severity	Integer
depression_diagnosis	Indicates if the patient has comorbid depression (Yes/No)	Text
anxiety_diagnosis	Indicates if the patient has comorbid anxiety (Yes/No)	Text
medications	Medication prescribed (e.g., SSRI, SNRI, Benzodiazepine, None)	Text
<img width="1084" height="523" alt="image" src="https://github.com/user-attachments/assets/ddf3e272-8a82-423f-ad00-71066fb7d431" />


