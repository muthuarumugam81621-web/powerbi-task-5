# 🏥 Healthcare Data Cleaning & Star Schema Modelling using Power BI

## 📌 Project Overview

This project focuses on cleaning healthcare data and building a **Star Schema Data Model** using Microsoft Power BI. It uses Power Query Editor to clean and transform healthcare records and creates dimension tables and a fact table for clinical data analysis.

The project prepares structured healthcare data for reporting, visualization, and analytical purposes.

## 🎯 Objectives

- Clean and transform healthcare datasets using Power Query.
- Correct data types and standardize text values.
- Remove exact duplicate records.
- Categorize patients into age groups.
- Create dimension tables for patients, doctors, hospitals, and dates.
- Build a central FactAdmission table.
- Establish relationships using a Star Schema model.

## 🛠️ Technologies Used

- **Microsoft Power BI Desktop**
- **Power Query Editor**
- **Power BI Model View**
- **CSV Dataset**

## 📂 Dataset Information

- **Dataset:** `healthcare_dataset(2).csv`
- **Original Records:** 55,500 rows
- **Columns:** 15

### Dataset Columns

- Name
- Age
- Gender
- Blood Type
- Medical Condition
- Date of Admission
- Doctor
- Hospital
- Insurance Provider
- Billing Amount
- Room Number
- Admission Type
- Discharge Date
- Medication
- Test Results

## 🧹 Data Cleaning and Transformation

The following operations were performed in Power Query:

1. Loaded the healthcare CSV dataset.
2. Renamed the base query to `Healthcare_Cleaned`.
3. Assigned appropriate data types to all columns.
4. Applied Trim and Clean operations to text columns.
5. Standardized patient names using Capitalize Each Word.
6. Removed 534 exact duplicate records.
7. Created an `AgeGroup` column.
8. Standardized admission types as Emergency, Elective, and Urgent.

### Age Group Categories

| Age Range | Category |
|---|---|
| 0–17 | Pediatric |
| 18–39 | Young Adult |
| 40–59 | Middle Adult |
| 60 and above | Senior |

## ⭐ Star Schema Data Model

The project contains six tables:

| Table Name | Purpose |
|---|---|
| `Healthcare_Cleaned` | Cleaned base dataset |
| `DimPatient` | Patient details and PatientID |
| `DimDoctor` | Doctor details and DoctorID |
| `DimHospital` | Hospital details and HospitalID |
| `DimDate` | Date, year, month, month number, and quarter |
| `FactAdmission` | Admission records and measurable details |

### Model Relationships

The `FactAdmission` table is connected to four dimension tables.

- `DimPatient[PatientID]` → `FactAdmission[PatientID]`
- `DimDoctor[DoctorID]` → `FactAdmission[DoctorID]`
- `DimHospital[HospitalID]` → `FactAdmission[HospitalID]`
- `DimDate[Date]` → `FactAdmission[Date of Admission]`

All four relationships use **one-to-many (1:*) cardinality** and single-direction cross-filtering.

## 📊 Key Features

- Healthcare data cleaning and preprocessing
- Duplicate record removal
- Patient demographic categorization
- Standardized admission types
- Surrogate key generation
- Fact and dimension table creation
- Star Schema modelling
- Date dimension with year, month, and quarter
- Data model preparation for clinical analytics

## 🚀 How to Run the Project

1. Install and open Microsoft Power BI Desktop.
2. Download or obtain the healthcare CSV dataset.
3. Open Power BI Desktop.
4. Select **Home → Get Data → Text/CSV**.
5. Import `healthcare_dataset(2).csv`.
6. Select **Transform Data** to open Power Query Editor.
7. Follow the data cleaning and transformation steps.
8. Create the dimension tables and `FactAdmission`.
9. Create `DimDate` using Power Query Advanced Editor.
10. Select **Close & Apply**.
11. Open Model View and configure the four relationships.
12. Verify the final Star Schema.

## 📈 Expected Outcome

A cleaned healthcare data model with patient, doctor, hospital, and date dimensions connected to a central admission fact table. The model is structured to support future Power BI reports and clinical data analysis.

## 🎓 Learning Outcomes

- Understanding data cleaning with Power Query
- Working with healthcare datasets
- Creating dimension and fact tables
- Generating surrogate keys
- Understanding Star Schema architecture
- Creating and managing Power BI relationships

## 👨‍💻 Project Type

Academic / Data Analytics Project

## 📄 Documentation

Refer to `PowerBI_Healthcare_Star_Schema_Guide.pdf` for the detailed, step-by-step implementation guide.

---

**If you find this project useful, consider giving the repository a ⭐ on GitHub.**
