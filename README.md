**INSIGHTFUL:** **Insight Generation through Clinical Annotation, Analysis, and Modeling of Suicide-Related Factors towards Understanding and Lifesaving**

## Project Overview

**INSIGHTFUL** is a research project focused on extracting and classifying suicidal phenotypes—such as suicidal ideation, suicide attempt, exposure to suicide, and non-suicidal self-injury (NSSI)—from unstructured psychiatric evaluation notes using state-of-the-art Reasoning Language Models (RLMs). The project introduces a high-quality, clinically annotated dataset of 500 inpatient psychiatric evaluation notes from a safety-net hospital in Harris County, Texas.

Our goal is to:
- Create a publicly accessible, de-identified dataset with annotated suicidality labels.
- Develop and evaluate multi-label classification methods using reasoning LLMs like GPT-4o, o3-mini, and o1.
- Provide structured clinical justification to enhance interpretability and explainability in mental health AI applications.

All labels and outputs are validated against a gold-standard annotated corpus with Cohen’s Kappa of 0.95, indicating near-perfect agreement.

## Label Dictionary
| Label                    | Abbreviation | Description                                                          |
| ------------------------ | ------------ | -------------------------------------------------------------------- |
| Suicidal Ideation        | SI           | Thoughts or verbalizations of wanting to end one’s life              |
| Suicide Attempt          | SA           | Actions taken with the intent to end one’s life                      |
| Exposure to Suicide      | ES           | Patient has lost someone to suicide or witnessed a suicide           |
| Non-Suicidal Self-Injury | NSSI         | Self-harming behavior with no intent to die (e.g., cutting, burning) |
| None-Suicidal            | NS           | Absence of any of Ideation or Attempt, regardless of NSSI or ES      |


## Metadata Schema

| Field Name            | Type     | Description                                                  |
| --------------------- | -------- | ------------------------------------------------------------ |
| **PatientID**         | String   | De-identified patient identifier (ClientGUID)                |
| **VisitID**           | String   | Unique visit identifier (VisitGUID)                          |
| **BirthYear**         | Integer  | Year of birth of the patient (BirthYearNum)                  |
| **Age**               | Integer  | Patient’s age at time of admission (years)                   |
| **Gender**            | String   | Patient gender code (GenderCode)                             |
| **Race**              | String   | Patient race code (RaceCode)                                 |
| **MaritalStatus**     | String   | Patient marital status code (MaritalStatusCode)              |
| **Religion**          | String   | Patient religion code (ReligionCode)                         |
| **Language**          | String   | Patient primary language code (LanguageCode)                 |
| **AdmitDateTime**     | DateTime | Date and time of hospital admission (AdmitDtm)               |
| **DischargeDateTime** | DateTime | Date and time of hospital discharge (DischargeDtm)           |
| **LoS**               | Integer  | Number of days between AdmitDtm and DischargeDtm (LoS)       |
| **VisitType**         | String   | Type of visit, e.g. inpatient vs. outpatient (visit\_type)   |
| **CareLevel**         | String   | Level of care setting (care\_level)                          |
| **Provider_ID**       | String   | Unique identifier for provider (Pro_ID)                      |
| **DocumentName**      | String   | Clinical note section or document name (DisplayName)         |
| **NoteText**          | Text     | Concatenated full text of all relevant sections (ValueText)  |
| **NS**                | Integer  | None-suicidal (1=yes, 0=no)                                  |
| **SI**                | Integer  | Suicidal Ideation (1=yes, 0=no)                              |
| **SA**                | Integer  | Suicide Attempt (1=yes, 0=no)                                |
| **ES**                | Integer  | Other’s Suicide (1=yes, 0=no)                                |
| **NSSI**              | Integer  | Non-Suicidal Self-Injury (1=yes, 0=no)                       |



## Sample Data Format

```json
{
  "PatientID": "P-0001",
  "VisitID": "V-1001",
  "BirthYear": 1987,
  "Age": 36,
  "Gender": "Female",
  "Race": "Non Denom. Christian",
  "MaritalStatus": "Single",
  "Religion": "Other Christian",
  "Language": "English",
  "AdmitDateTime": "2018-03-12T09:45:00",
  "DischargeDateTime": "2018-03-17T14:20:00",
  "LoS": 5,
  "VisitType": "Inpatient",
  "CareLevel": "Psychiatry",
  "Provider_ID": "Pro-01",
  "DocumentName": "Initial Psychiatric Evaluation",
  "NoteText": "Patient reports increasing anxiety over the past month with occasional thoughts of self-harm. Denies any plan or intent to act. History of non-suicidal cutting 2 years ago.",
  "Labels": {
    "NS": 0,
    "SI": 1,
    "SA": 0,
    "ES": 0,
    "NSSI": 1
  }
```

## Access and Licensing
This dataset is shared for academic and research use under a Data Use Agreement (DUA). Please contact the corresponding author for access.

License: UTHealth Houston License

## Contact
For inquiries, dataset access, or collaboration opportunities, please contact:

Zehan (Leo) Li
Ph.D. Candidate, UTHealth Houston
Email: zehan.li@uth.tmc.edu
