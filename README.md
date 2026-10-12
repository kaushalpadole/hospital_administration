# Hospital Administration Analytics: Readmission Analysis in Excel

## Project Overview

This project analyzes hospital encounter data to explore patterns associated with 30-day readmission, length of hospital stay, patient demographics, medication indicators, and prior healthcare utilization. The analysis and dashboard are built in Microsoft Excel using PivotTables, PivotCharts, formulas, and descriptive statistics.

The objective is to turn the available hospital data into understandable metrics and visuals that could help identify areas for further investigation. The analysis is descriptive: observed associations do not establish causation.

## Dashboard

![Hospital Readmission Analysis Dashboard](images/hospital-readmission-dashboard.png)

The dashboard includes KPI cards and PivotCharts for:
- Total records
- Unique patients
- Overall readmission rate
- Average length of stay
- Readmission by weight range
- Readmission rate by age and gender
- Readmission by age group
- Average length of stay by the top 10 medical specialties
- Readmission by medication-change status
- Readmission status by diabetes-medication status

## Key Dashboard Metrics

| Metric | Value |
|---|---:|
| Total records | 66,587 |
| Unique patients | 39,650 |
| Readmission rate | Approximately 46.20% |
| Average length of stay | Approximately 4.40 days |

The dataset contains repeated records/encounters, so record count, unique patient count, and unique encounter count are different measures. The dashboard's record count represents rows in the analyzed dataset.

## Tools and Techniques

- **Microsoft Excel**
- Excel Tables and structured references
- PivotTables and PivotCharts
- Average of the binary `readmitted` field to calculate readmission proportions
- `CORREL` for basic correlation checks
- Data grouping and sorting for age ranges, utilization counts, and top specialties
- Dashboard layout, KPI cards, chart titles, labels, and formatting

## Analysis Included

The README intentionally includes only questions that can be meaningfully explored with the available fields. Questions requiring unavailable data and the predictive-model question are excluded.

### Basic-level analysis

1. **Age group and readmission:** Compare the average of `readmitted` across age groups.
2. **Medical specialty and length of stay:** Compare average `time_in_hospital` by `medical_specialty`; rank specialties by average stay.
3. **Emergency visits and readmission:** Check the relationship between `number_emergency` and `readmitted`. The calculated correlation was approximately **0.108**, a weak positive association.
4. **Diabetes medication and readmission:** Compare average `readmitted` for `diabetesMed = Yes` and `No`. The dashboard shows approximately **47.96%** for `Yes` and **40.34%** for `No`.
5. **Medication change and readmission:** Compare readmission proportions for the `change` categories. The observed difference was approximately **4.49 percentage points** in the prior analysis; this is descriptive, not a test of statistical significance.
6. **Lab procedures and readmission:** The correlation between `num_lab_procedures` and `readmitted` was approximately **0.036**, a very weak positive association.
7. **Race, gender, and readmission:** Use a PivotTable with race and gender categories and average `readmitted`.
8. **Weight and readmission:** Compare readmission proportions across recorded weight ranges. Weight is missing for approximately **97%** of records, so this analysis has substantial limitations and should be interpreted cautiously.
9. **Number of medications and length of stay:** The correlation between `num_medications` and `time_in_hospital` was approximately **0.466**, a moderate positive association.
10. **Outpatient visits and readmission:** The correlation between `number_outpatient` and `readmitted` was approximately **0.082**, a very weak positive association.

### Medium-level analysis

12. **Number of diagnoses and outcomes:** `number_diagnoses` had a correlation of approximately **0.218** with length of stay and **0.107** with `readmitted`. These are weak positive associations.
14. **Demographics and care interventions:** Compare average lab procedures and medication counts across available demographic groups such as race, gender, and age.
15. **Primary diagnosis and prior healthcare utilization:** Use `diag_1` to compare average inpatient, outpatient, and emergency visit counts. Consider focusing on frequently occurring diagnoses so the PivotTable remains readable.
17. **Medication indicators by specialty and readmission:** Unpivot medication-indicator fields where needed, then use PivotTables to compare recorded medication statuses across specialties and readmission groups. Medication indicators and status labels should be interpreted descriptively.
18. **Weight, primary diagnosis, and readmission:** Compare average readmission proportions across available weight categories and primary diagnoses. The high level of missing weight data limits the strength of conclusions.
19. **Diabetes medication indicators and readmission:** Filter to records where `diabetesMed = Yes`, then compare available medication indicators/statuses against readmission proportions. These comparisons do not establish medication effectiveness or causality.

### Advanced-level analysis included

22. **Descriptive patient utilization segmentation:** Summarize `number_inpatient`, `number_outpatient`, and `number_emergency` by patient and compare the summaries with readmission. This is an exploratory grouping exercise, not a predictive model.
24. **Available demographic factors:** Explore readmission patterns by the available race, gender, and age fields. These fields provide only a partial view of social determinants and should not be treated as a complete social-risk assessment.

## Findings and Interpretation

- The overall readmission proportion in the analyzed records is approximately **46.20%**.
- Records with `diabetesMed = Yes` have a higher observed readmission proportion than records with `diabetesMed = No` in this dataset.
- The relationship between number of medications and length of stay is more noticeable than the correlations observed for emergency visits, outpatient visits, or lab procedures.
- Average length of stay varies across medical specialties.
- Weight-based comparisons are especially uncertain because most weight values are missing.
- These results describe patterns in this dataset; they do not demonstrate that any individual factor causes readmission.

## Scope and Limitations

The following question areas are intentionally omitted because the dataset does not contain the required information, or because they are outside the scope of this Excel analysis:

- **Time-based readmission trends:** no suitable encounter date/time field is available.
- **Discharge disposition:** the required discharge-disposition field is unavailable.
- **Long-term outcomes:** mortality and post-discharge follow-up outcome data are unavailable.
- **Patient satisfaction:** satisfaction or survey data are unavailable.
- **Predictive modeling:** the predictive-model question is excluded because it is beyond the scope of this Excel-based descriptive project.
- **Financial impact:** cost data and criteria for preventable readmissions are unavailable.
- **Measured impact of post-discharge interventions:** intervention and follow-up outcome data are not available to quantify an effect.

Other limitations include missing weight data, potential repeated records, and the fact that correlation does not imply causation. Readmission proportions should be interpreted in the context of group sizes and available fields.

## Workbook Structure

The Excel workbook is organized around the source data and analysis outputs, including a dedicated **Dashboard** sheet for the KPI cards and PivotCharts. Supporting PivotTables and intermediate analysis can be kept on separate analysis sheets so the dashboard remains readable.

## How to Use

1. Open the Excel workbook.
2. Review the `Dashboard` sheet for the headline metrics and visual summaries.
3. Review the supporting PivotTables and calculations on the analysis sheets.
4. Refresh PivotTables after changing or replacing the source data.
5. Verify that the PivotTable source range covers the intended dataset before interpreting totals.

## Disclaimer

This project is for educational and exploratory analytics purposes. It is not a clinical decision-support system and should not be used to make patient-care decisions. All findings are descriptive and should be validated before operational use.
