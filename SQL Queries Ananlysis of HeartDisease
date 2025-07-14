CREATE DATABASE HeartDiseaseDB;

USE HeartDiseaseDB;

CREATE TABLE HeartDiseaseDataset (
    PatientID INT PRIMARY KEY,                 -- Unique identifier for each patient
    Age INT,                                   -- Age of the patient
    Gender VARCHAR(10),                        -- Gender (Male, Female, Other)
    Ethnicity VARCHAR(50),                     -- Ethnic background
    Occupation VARCHAR(100),                   -- Occupation of the patient
    
    FamilyHistory BIT,                         -- Whether the patient has family history of heart disease (Yes/No)
    PreviousHeartDisease BIT,                  -- Whether the patient has a history of heart disease (Yes/No)
    Diabetes BIT,                              -- Whether the patient has diabetes (Yes/No)
    Hypertension BIT,                          -- Whether the patient has high blood pressure (Yes/No)
    StrokeHistory BIT,                         -- Whether the patient has a history of stroke (Yes/No)
    ChronicKidneyDisease BIT,                  -- Whether the patient has chronic kidney disease (Yes/No)
    
    CholesterolLevel INT,                      -- Total cholesterol level (in mg/dL)
    HDLCholesterol INT,                        -- HDL cholesterol level (in mg/dL)
    LDLCholesterol INT,                        -- LDL cholesterol level (in mg/dL)
    Triglycerides INT,                         -- Triglyceride level (in mg/dL)
    BloodPressureSystolic INT,                 -- Systolic blood pressure (in mmHg)
    BloodPressureDiastolic INT,                -- Diastolic blood pressure (in mmHg)
    BodyMassIndex DECIMAL(5,2),                -- BMI (in kg/m²)
    HeartRate INT,                             -- Resting heart rate (beats per minute)
    WaistCircumference DECIMAL(5,2),           -- Waist circumference (in cm)
    ECGResult VARCHAR(20),                     -- ECG result (Normal/Abnormal)
    EchocardiogramResult VARCHAR(20),          -- Echocardiogram result (Normal/Abnormal)
    
    SmokingStatus BIT,                         -- Whether the patient smokes (Yes/No)
    AlcoholConsumption BIT,                    -- Whether the patient drinks alcohol (Yes/No)
    PhysicalActivity VARCHAR(50),              -- Physical activity level (None, 1-2 times a week, 3-5 times a week, etc.)
    DietType VARCHAR(50),                      -- Diet type (e.g., High-fat, Mediterranean, Vegan)
    DietarySodiumIntake INT,                   -- Sodium intake (in mg/day)
    SleepPatterns VARCHAR(50),                 -- Sleep patterns (hours per night)
    StressLevel INT,                           -- Self-reported stress level (1-10 scale)
    AlcoholUnits INT,                          -- Alcohol units consumed per week
    
    CurrentMedications VARCHAR(200),           -- List of current medications (e.g., statins, aspirin)
    SurgicalHistory VARCHAR(200),              -- History of heart-related surgeries (e.g., bypass, stents)
    HeartDiseaseTreatment VARCHAR(100),        -- Type of heart disease treatment (Medications, Surgery, Lifestyle Changes)
    
    HeartDiseaseDiagnosis BIT,                 -- Whether the patient has been diagnosed with heart disease (Yes/No)
    TypeOfHeartDisease VARCHAR(100),           -- Specific type of heart disease (e.g., Coronary Artery Disease, Heart Failure)
    HeartDiseaseSeverity VARCHAR(20),          -- Severity of heart disease (Mild, Moderate, Severe)
    HeartAttackHistory BIT,                    -- Whether the patient has had a heart attack (Yes/No)
    Angina BIT,                                -- Whether the patient experiences angina (chest pain) (Yes/No)
    
    PreventiveCareVisits INT,                  -- Number of preventive care visits in the past year
    VaccinationStatus BIT,                     -- Whether the patient has received vaccinations like flu, pneumonia (Yes/No)
    LifestyleModificationPrograms BIT,         -- Whether the patient has participated in lifestyle modification programs (Yes/No)
    WeightManagementStatus BIT,                -- Whether the patient is actively managing their weight (Yes/No)
    BloodPressureControl BIT,                  -- Whether the patient has their blood pressure under control (Yes/No)
    
    FollowUpVisits BIT,                        -- Whether the patient attends regular follow-up visits (Yes/No)
    HospitalizationHistory BIT,                -- Whether the patient has been hospitalized for heart disease (Yes/No)
    MortalityStatus VARCHAR(20),               -- Mortality status (Alive, Deceased) and date of death (if applicable)
    Outcome VARCHAR(100)                       -- Outcome of heart disease treatment (Improvement, No Change, Worsening)
);

-- Insert 30,000 rows of random data
DECLARE @counter INT = 1;

WHILE @counter <= 30000
BEGIN
    INSERT INTO HeartDiseaseDataset (
        PatientID, Age, Gender, Ethnicity, Occupation,
        FamilyHistory, PreviousHeartDisease, Diabetes, Hypertension, StrokeHistory, ChronicKidneyDisease,
        CholesterolLevel, HDLCholesterol, LDLCholesterol, Triglycerides, BloodPressureSystolic, BloodPressureDiastolic,
        BodyMassIndex, HeartRate, WaistCircumference, ECGResult, EchocardiogramResult,
        SmokingStatus, AlcoholConsumption, PhysicalActivity, DietType, DietarySodiumIntake, SleepPatterns,
        StressLevel, AlcoholUnits,
        CurrentMedications, SurgicalHistory, HeartDiseaseTreatment,
        HeartDiseaseDiagnosis, TypeOfHeartDisease, HeartDiseaseSeverity, HeartAttackHistory, Angina,
        PreventiveCareVisits, VaccinationStatus, LifestyleModificationPrograms, WeightManagementStatus, BloodPressureControl,
        FollowUpVisits, HospitalizationHistory, MortalityStatus, Outcome
    )
    VALUES (
        @counter,                                    -- PatientID
        ABS(CHECKSUM(NEWID()) % 90) + 18,            -- Age (random between 18 and 108)
        CASE WHEN RAND() < 0.5 THEN 'Male' ELSE 'Female' END,   -- Gender (random Male/Female)
        CASE WHEN RAND() < 0.2 THEN 'Caucasian' WHEN RAND() < 0.4 THEN 'African American' WHEN RAND() < 0.6 THEN 'Hispanic' ELSE 'Asian' END,  -- Ethnicity
        CASE WHEN RAND() < 0.5 THEN 'Office Worker' ELSE 'Laborer' END, -- Occupation
        CASE WHEN RAND() < 0.7 THEN 1 ELSE 0 END,   -- FamilyHistory (Yes/No)
        CASE WHEN RAND() < 0.5 THEN 1 ELSE 0 END,   -- PreviousHeartDisease (Yes/No)
        CASE WHEN RAND() < 0.2 THEN 1 ELSE 0 END,   -- Diabetes (Yes/No)
        CASE WHEN RAND() < 0.3 THEN 1 ELSE 0 END,   -- Hypertension (Yes/No)
        CASE WHEN RAND() < 0.15 THEN 1 ELSE 0 END,  -- StrokeHistory (Yes/No)
        CASE WHEN RAND() < 0.1 THEN 1 ELSE 0 END,   -- ChronicKidneyDisease (Yes/No)
        ABS(CHECKSUM(NEWID()) % 301) + 100,         -- CholesterolLevel (random between 100 and 400)
        ABS(CHECKSUM(NEWID()) % 101) + 30,          -- HDLCholesterol (random between 30 and 130)
        ABS(CHECKSUM(NEWID()) % 151) + 50,          -- LDLCholesterol (random between 50 and 200)
        ABS(CHECKSUM(NEWID()) % 200) + 50,          -- Triglycerides (random between 50 and 250)
        ABS(CHECKSUM(NEWID()) % 51) + 100,          -- BloodPressureSystolic (random between 100 and 150)
        ABS(CHECKSUM(NEWID()) % 41) + 60,           -- BloodPressureDiastolic (random between 60 and 100)
        CAST(ROUND(RAND() * 30 + 15, 2) AS DECIMAL(5,2)), -- BMI (random between 15 and 45)
        ABS(CHECKSUM(NEWID()) % 61) + 60,           -- HeartRate (random between 60 and 120)
        ABS(CHECKSUM(NEWID()) % 51) + 60,           -- WaistCircumference (random between 60 and 110)
        CASE WHEN RAND() < 0.1 THEN 'Abnormal' ELSE 'Normal' END, -- ECGResult
        CASE WHEN RAND() < 0.1 THEN 'Abnormal' ELSE 'Normal' END, -- EchocardiogramResult
        CASE WHEN RAND() < 0.4 THEN 1 ELSE 0 END,   -- SmokingStatus (Yes/No)
        CASE WHEN RAND() < 0.5 THEN 1 ELSE 0 END,   -- AlcoholConsumption (Yes/No)
        CASE WHEN RAND() < 0.7 THEN 'None' WHEN RAND() < 0.85 THEN '1-2 times a week' ELSE '3-5 times a week' END, -- PhysicalActivity
        CASE WHEN RAND() < 0.3 THEN 'High-fat' WHEN RAND() < 0.6 THEN 'Mediterranean' ELSE 'Vegan' END, -- DietType
        ABS(CHECKSUM(NEWID()) % 5000) + 1000,       -- DietarySodiumIntake (mg/day)
        ABS(CHECKSUM(NEWID()) % 12) + 4,            -- SleepPatterns (random between 4 and 16 hours)
        ABS(CHECKSUM(NEWID()) % 11) + 1,            -- StressLevel (random between 1 and 10)
        ABS(CHECKSUM(NEWID()) % 21),                -- AlcoholUnits (random between 0 and 20)
        'None',                                     -- CurrentMedications
        'None',                                     -- SurgicalHistory
        'None',                                     -- HeartDiseaseTreatment
        CASE WHEN RAND() < 0.3 THEN 1 ELSE 0 END,   -- HeartDiseaseDiagnosis (Yes/No)
        CASE WHEN RAND() < 0.5 THEN 'Coronary Artery Disease' ELSE 'Heart Failure' END,  -- TypeOfHeartDisease
        CASE WHEN RAND() < 0.5 THEN 'Mild' ELSE 'Severe' END,  -- HeartDiseaseSeverity
        CASE WHEN RAND() < 0.2 THEN 1 ELSE 0 END,   -- HeartAttackHistory (Yes/No)
        CASE WHEN RAND() < 0.3 THEN 1 ELSE 0 END,   -- Angina (Yes/No)
        ABS(CHECKSUM(NEWID()) % 10),                -- PreventiveCareVisits (random between 0 and 10)
        CASE WHEN RAND() < 0.7 THEN 1 ELSE 0 END,   -- VaccinationStatus (Yes/No)
        CASE WHEN RAND() < 0.5 THEN 1 ELSE 0 END,   -- LifestyleModificationPrograms (Yes/No)
        CASE WHEN RAND() < 0.6 THEN 1 ELSE 0 END,   -- WeightManagementStatus (Yes/No)
        CASE WHEN RAND() < 0.8 THEN 1 ELSE 0 END,   -- BloodPressureControl (Yes/No)
        CASE WHEN RAND() < 0.8 THEN 1 ELSE 0 END,   -- FollowUpVisits (Yes/No)
        CASE WHEN RAND() < 0.4 THEN 1 ELSE 0 END,   -- HospitalizationHistory (Yes/No)
        CASE WHEN RAND() < 0.95 THEN 'Alive' ELSE 'Deceased' END,  -- MortalityStatus (Alive/Deceased)
        CASE WHEN RAND() < 0.95 THEN 'Improvement' ELSE 'Worsening' END  -- Outcome
    );
    
    SET @counter = @counter + 1;
END;

SELECT * FROM HeartDiseaseDataset;

--1. Demographic Analysis: Age Distribution and Gender-based Risk.

--QUERY 1: Heart Disease Diagnosis by Age Group and Gender

CREATE VIEW AgeGenderHeartDiseaseAnalysis AS
SELECT 
    CASE
        WHEN Age BETWEEN 18 AND 30 THEN '18-30'
        WHEN Age BETWEEN 31 AND 40 THEN '31-40'
        WHEN Age BETWEEN 41 AND 50 THEN '41-50'
        WHEN Age BETWEEN 51 AND 60 THEN '51-60'
        WHEN Age BETWEEN 61 AND 70 THEN '61-70'
        WHEN Age > 70 THEN '71+'
    END AS AgeGroup,
    Gender,
    COUNT(*) AS TotalPatients,
    SUM(CAST(HeartDiseaseDiagnosis AS INT)) AS DiagnosedWithHeartDisease,
    CAST(SUM(CAST(HeartDiseaseDiagnosis AS INT)) AS FLOAT) / COUNT(*) * 100 AS DiagnosisPercentage
FROM HeartDiseaseDataset
GROUP BY 
    CASE
        WHEN Age BETWEEN 18 AND 30 THEN '18-30'
        WHEN Age BETWEEN 31 AND 40 THEN '31-40'
        WHEN Age BETWEEN 41 AND 50 THEN '41-50'
        WHEN Age BETWEEN 51 AND 60 THEN '51-60'
        WHEN Age BETWEEN 61 AND 70 THEN '61-70'
        WHEN Age > 70 THEN '71+'
    END,  -- Same CASE expression in GROUP BY
    Gender;

SELECT * FROM AgeGenderHeartDiseaseAnalysis;

--2. Risk Factors Analysis: Smoking, Diabetes, and Hypertension.

--QUERY 2: Heart Disease Diagnosis by Risk Factors.

CREATE VIEW RiskFactorAnalysis AS
SELECT 
    SmokingStatus,
    Diabetes,
    Hypertension,
    COUNT(*) AS TotalPatients,
    SUM(CAST(HeartDiseaseDiagnosis AS INT)) AS DiagnosedWithHeartDisease,
    CAST(SUM(CAST(HeartDiseaseDiagnosis AS INT)) AS FLOAT) / COUNT(*) * 100 AS DiagnosisPercentage
FROM HeartDiseaseDataset
GROUP BY SmokingStatus, Diabetes, Hypertension;

SELECT * FROM RiskFactorAnalysis;

--3.Correlation Analysis: Cholesterol and Blood Pressure with Heart Disease.

--QUERY 3: Cholesterol and Blood Pressure Levels vs Heart Disease Diagnosis.

CREATE VIEW CorrelationAnalysis AS
SELECT 
    CholesterolLevel,
    BloodPressureSystolic,
    BloodPressureDiastolic,
    COUNT(*) AS TotalPatients,
    SUM(CAST(HeartDiseaseDiagnosis AS INT)) AS DiagnosedWithHeartDisease,
    CAST(SUM(CAST(HeartDiseaseDiagnosis AS INT)) AS FLOAT) / COUNT(*) * 100 AS DiagnosisPercentage
FROM HeartDiseaseDataset
WHERE CholesterolLevel IS NOT NULL AND BloodPressureSystolic IS NOT NULL
GROUP BY CholesterolLevel, BloodPressureSystolic, BloodPressureDiastolic;

SELECT * FROM CorrelationAnalysis;

--4. Outcome Analysis: Treatment and Outcome of Heart Disease.

-- QUERY 4: Heart Disease Treatment Outcome.

CREATE VIEW OutcomeAnalysis AS
SELECT 
    HeartDiseaseTreatment,
    COUNT(*) AS TotalPatients,
    SUM(CASE WHEN Outcome = 'Improvement' THEN 1 ELSE 0 END) AS ImprovedPatients,
    SUM(CASE WHEN Outcome = 'Worsening' THEN 1 ELSE 0 END) AS WorsenedPatients,
    SUM(CASE WHEN Outcome = 'No Change' THEN 1 ELSE 0 END) AS NoChangePatients
FROM HeartDiseaseDataset
GROUP BY HeartDiseaseTreatment;

SELECT * FROM OutcomeAnalysis;

--5 Preventive Care: Visits and Effectiveness.

--QUERY 5: Preventive Care Visits vs Diagnosis Outcome.

CREATE VIEW PreventiveCare AS
SELECT 
    PreventiveCareVisits,
    COUNT(*) AS TotalPatients,
    SUM(CASE WHEN HeartDiseaseDiagnosis = 1 THEN 1 ELSE 0 END) AS DiagnosedWithHeartDisease,
    SUM(CASE WHEN Outcome = 'Improvement' THEN 1 ELSE 0 END) AS ImprovedPatients
FROM HeartDiseaseDataset
GROUP BY PreventiveCareVisits;

SELECT * FROM PreventiveCare;

--QUERY 1: Heart Disease Diagnosis by Age Group and Gender
SELECT * FROM AgeGenderHeartDiseaseAnalysis;

--QUERY 2: Heart Disease Diagnosis by Risk Factors
SELECT * FROM RiskFactorAnalysis;

--QUERY 3: Cholesterol and Blood Pressure Levels vs Heart Disease Diagnosis
SELECT * FROM CorrelationAnalysis;

-- QUERY 4: Heart Disease Treatment Outcome
SELECT * FROM OutcomeAnalysis;

--QUERY 5: Preventive Care Visits vs Diagnosis Outcome
SELECT * FROM PreventiveCare;



