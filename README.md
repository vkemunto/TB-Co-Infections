# TB-Co-Infections


Name: Violet Kemunto
Adm. No: 193341
Introduction
    1.0. Background
Tuberculosis (TB) and Human Immunodeficiency Virus (HIV) are two major public health concerns worldwide, each posing significant challenges to healthcare systems. TB remains one of the leading causes of illness and death among people living with HIV, including those on antiretroviral therapy (ART). The co-infection of TB and HIV creates a complex clinical scenario, where the immune suppression caused by HIV increases the susceptibility to TB, and TB accelerates the progression of HIV disease. Therefore, timely TB treatment and early initiation of ART are essential for reducing mortality rates associated with HIV-TB co-infection. This project aims to develop a predictive model to identify HIV patients at high risk of developing TB. By leveraging socio-demographic, clinical, and behavioural data, the model seeks to enhance early detection, improve intervention strategies, and ultimately reduce TB-related mortality among HIV patients.
        1.1. Research Problem
The high incidence of TB among HIV patients reveals a critical gap in the current healthcare framework. Despite advancements in diagnostic and treatment protocols, the complex interplay between TB and HIV often remains inadequately addressed. This project aims to fill this gap by developing a robust predictive model that integrates multiple factors to accurately predict TB risk in HIV patients. This model will facilitate timely and targeted interventions, improving patient outcomes and reducing the overall burden of TB in the HIV-infected population. The dual burden of TB and HIV significantly worsens health outcomes, underscoring the need for early detection, effective treatment, and preventive strategies. Addressing this dual burden requires coordinated efforts from both the AIDS Programme and National TB Programme to implement integrated care strategies that can identify and manage TB in HIV patients efficiently.
        1.2. Objectives
1. Create a Predictive Model for Tuberculosis co-infections 
Specific: Build a model that uses demographic, clinical, and treatment information to estimate the likelihood of TB in HIV patients. 
Measurable: Aim for a model accuracy of at least 85% and a precision-recall score of 0.8 or better based on validation results.
Achievable: Utilize the data from KenyaEMR and apply machine learning methods like logistic regression and random forests. 
Relevant: Improve TB risk prediction to better manage and treat HIV patients. Time-bound: Complete the model by July 25, 2024.
2.  Determine Major Risk Factors for TB in HIV Patients
Specific: Identify the most important factors contributing to TB risk among HIV patients, focusing on variables such as ART adherence and IPT status.
Measurable: Highlight the top five risk factors based on their influence on TB risk, with supporting statistical evidence. 
Achievable: Use data analysis and feature importance techniques to discover these key factors.
Relevant: Provide insights that can help in developing targeted prevention and treatment strategies. 
3.  Assess and Compare Machine Learning Algorithms for TB Prediction: 
Specific: Evaluate and contrast different machine learning algorithms (e.g., logistic regression, decision trees, random forests) to predict TB risk.
Measurable: Compare models based on performance metrics such as accuracy, precision, recall, and F1-score to identify the best-performing algorithm. 
Achievable: Train and test various models using the provided dataset and analyse their performance.
Relevant: Choose the most effective algorithm for practical TB risk prediction. 

        1.3. Hypothesis
    1. Among HIV patients, those with poorer adherence to antiretroviral therapy (ART), higher levels of smoking, and a history of non-communicable diseases (NCDs) are at a significantly higher risk of developing tuberculosis (TB). The inclusion of these factors in a predictive model will improve its accuracy in forecasting TB risk
    2. The presence of specific clinical symptoms (such as cough, fever, and weight loss) and the status of Isoniazid Preventive Therapy (IPT) will significantly influence the likelihood of an HIV patient being diagnosed with active tuberculosis (TB). Incorporating these variables into the predictive model will enhance its capability to identify high-risk patients.

        1.4. Methodology, Result and Discussion
The data for this study is sourced from patient-level records maintained within the KenyaEMR (Kenya Electronic Medical Records) system. This dataset spans the last six months, which aligns with the standard screening protocol for tuberculosis (TB) among HIV patients, where eligibility for screening requires that patients have undergone evaluations at least every six months. The data collection process involved using a consolidated script designed to extract relevant patient information from ETL (Extract, Transform, Load) tables, leveraging our internal data repository managed by Savannah Informatics. This script systematically pulls data from multiple sources to ensure a comprehensive dataset. The collection occurred under routine clinical conditions within healthcare facilities participating in the KenyaEMR network. During this period, patients were routinely assessed for TB risk factors and co-infections as part of their standard care procedures. The conditions included adherence to stringent data privacy and security protocols to safeguard patient information. Additionally, the data was gathered during regular health check-ups and screenings, ensuring it reflects the typical patient management and monitoring practices within the healthcare system. This approach helps maintain the integrity and relevance of the data for predictive modelling and subsequent analysis.
The table below contain variables that I will be working with on my model:



Variable Name
Description
Age
Age of the patient in years
Gender
Gender of the patient (Male/Female/Other)
Age groups
Categorized age groups (e.g., 0-18, 19-35, 36-50, 51+)
MaritalStatus
Marital status of the patient (e.g., Single, Married, Divorced, Widowed)
Occupation
Patient's occupation and its exposure risk (High/Medium/Low)
EducationLevel
Level of education attained by the patient
Population type
General or specific population groups (e.g., Key population type)
WHO staging
World Health Organization HIV/AIDS clinical staging
Start regimen
Initial antiretroviral therapy regimen
Start regimen line
Line of initial regimen (e.g., First-line, Second-line)
Current regimen
Current antiretroviral therapy regimen
Current regimen line
Line of current regimen (e.g., First-line, Second-line)
ART adherence
Adherence to antiretroviral therapy (Good/Poor)
NCDs
Presence of non-communicable diseases (e.g., diabetes, hypertension)
Nutritional status
Current nutritional status (e.g., Underweight, Normal, Overweight)
Lifestyle Modification
Lifestyle changes made by the patient (e.g., diet, exercise)
Previous Nutrition status
Previous nutritional status (e.g., Underweight, Normal, Overweight)
Has Chronic illness Comorbidities
Presence of chronic illnesses other than HIV (Yes/No)
Smoking status
Smoking status of the patient (Smoker/Non-smoker)
Alcohol use
Alcohol consumption (Yes/No)
Ever on IPT
Whether the patient has ever been on Isoniazid Preventive Therapy (Yes/No)
On IPT
Current status of Isoniazid Preventive Therapy (Yes/No)
Evaluated for IPT
Whether the patient has been evaluated for Isoniazid Preventive Therapy (Yes/No)
IPT outcome
Outcome of Isoniazid Preventive Therapy
IPT outcome date
Date of the Isoniazid Preventive Therapy outcome
Clinical TB diagnosis
Clinical diagnosis of tuberculosis (Yes/No)
Screened for TB
Whether the patient has been screened for tuberculosis (Yes/No)
TB Screening date
Date of the most recent TB screening
TB Screening status
Status of TB screening (e.g., Positive, Negative)
TB status
Current TB status (e.g., Active, Latent, No TB)
TB Status within last 6 months
TB status within the last six months (Yes/No)
On anti-TB drugs
Whether the patient is on anti-TB medication (Yes/No)
Lethargy
Presence of lethargy (Yes/No)
Cough
Presence of cough (Yes/No)
Fever
Presence of fever (Yes/No)
Weight_Loss_Poor_Gain
Weight loss or poor weight gain (Yes/No)
Night_Sweats
Presence of night sweats (Yes/No)
First_VL_Suppressed_or_Unsuppressed
Whether the first viral load is suppressed or unsuppressed (Suppressed/Unsuppressed)
Last VL result
Result of the most recent viral load test
Last_VL_Suppressed_or_Unsuppressed
Whether the last viral load is suppressed or unsuppressed (Suppressed/Unsuppressed)
Hypertension
Presence of hypertension (Yes/No)
Asthma
Presence of asthma (Yes/No)
