# QoF Call & Recall Master List — Product Specification

## Overview

A local-first browser application for NHS GP practices to consolidate Quality and Outcomes Framework (QoF) disease register exports into a single master patient list. Designed for practice administrators and clinical staff to identify multi-morbid and complex patients across all QoF registers.

## QoF Registers (14)

1. Asthma (AST)
2. Atrial Fibrillation (AF)
3. Cancer (CAN)
4. Chronic Kidney Disease (CKD)
5. Chronic Obstructive Pulmonary Disease (COPD)
6. Coronary Heart Disease (CHD)
7. Depression (DEP)
8. Diabetes Mellitus (DM)
9. Epilepsy (EPI)
10. Heart Failure (HF)
11. Hypertension (HYP)
12. Learning Disability (LD)
13. Mental Health (MH)
14. Stroke/TIA (STIA)

## Data Fields

- **Patient ID**: NHS Number (10 digits) or EMIS Number — primary merge key
- **Patient Name**: Full name, or Forename + Surname
- **DOB**: Date of birth
- **Register**: Which QoF condition the patient appears on

## Column Auto-Detection

The system detects columns by header name matching (case-insensitive):

| Field | Accepted Headers |
|-------|-----------------|
| NHS Number | NHS Number, NHS_No, NHS No, NHSNumber, Patient ID, PatientID |
| EMIS Number | EMIS Number, EMIS_No, EMIS ID, EMISNumber |
| Name | Patient Name, Name, Full Name, FullName, Forename, First Name, Surname, Last Name |
| DOB | DOB, Date of Birth, Date Of Birth, DateOfBirth, Birth Date, BirthDate |

Priority: NHS Number > EMIS Number for merge key.

## Processing Pipeline

1. **Ingest** — Parse CSV/XLSX files
2. **Detect** — Auto-detect column mappings per file
3. **Cross-reference** — Match patients across registers by ID
4. **Consolidate** — Merge into single row per patient
5. **Count** — Calculate condition count per patient
6. **Prioritise** — Sort by condition count descending

## Output

| Column | Description |
|--------|-------------|
| Patient ID | NHS or EMIS number |
| Patient Name | Best available name |
| DOB | Date of birth |
| Known QoF Conditions | Comma-separated list |
| Condition Count | Number of registers |

## Priority Classification

- **Complex** (red): ≥4 conditions
- **Multi-morbid** (amber): 2–3 conditions
- **Single** (green): 1 condition

## Export Formats

- CSV: `QoF_Master_List_YYYY-MM-DD.csv`
- Excel: `QoF_Master_List_YYYY-MM-DD.xlsx`
- JSON: `QoF_Master_List_YYYY-MM-DD.json`

## Privacy & Compliance

- 100% local processing — no data leaves the browser
- No server, no network calls, no analytics
- No data persistence — refresh clears everything
- Suitable for NHS patient data (no IG risk)

## Scale

- Target: 2,000–20,000 patients
- Processing time: seconds
- Works on any modern browser (Chrome, Edge, Firefox, Safari)

## Tech Stack

- Single HTML file + local SheetJS library
- Vanilla HTML5, CSS3, JavaScript (ES2022)
- No frameworks, no build tools, no server
