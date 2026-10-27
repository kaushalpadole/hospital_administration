# Hospital Administration Analytics — Readmission Analysis in Excel

## 1. Project Overview

This project explores hospital encounter data to understand patterns related to 30-day readmission, length of stay, patient demographics, medication indicators, and previous healthcare utilization. The analysis was completed in Microsoft Excel using PivotTables, PivotCharts, formulas, and a dashboard.

The purpose is to turn the available data into practical, descriptive insights that hospital administrators could investigate further. This is an exploratory analytics project: the results show associations and group differences, not proof of cause and effect.

**Google Drive link for Excel file:** https://docs.google.com/spreadsheets/d/15XtnVh7Oaucgz1a6vIqoaP75WhO7qbEQ/edit?usp=drive_link&ouid=106933887791179439291&rtpof=true&sd=true

## 2. Project Requirements

The project requirements were to:

- Inspect and analyze the supplied hospital dataset.
- Answer the case-study questions that can be supported by the available columns.
- Compare readmission proportions across patient and encounter categories.
- Explore factors associated with length of stay and prior healthcare utilization.
- Summarize important measures using KPI cards and charts.
- Present findings, limitations, and recommendations in a clear dashboard and README.

## 3. Dataset Summary

| Measure | Result |
|---|---:|
| Total rows / records | 66,587 |
| Unique patients | 39,650 |
| Overall readmission proportion | Approximately 46.20% |
| Average length of stay | Approximately 4.40 days |
| Weight values missing | Approximately 97% |

The dataset includes fields such as `patient_id`, `encounter_id`, `age`, `race`, `gender`, `weight`, `time_in_hospital`, `medical_specialty`, `num_lab_procedures`, `num_medications`, `number_outpatient`, `number_emergency`, `number_inpatient`, `number_diagnoses`, medication indicators, `change`, `diabetesMed`, and `readmitted`.

For interpretation, `readmitted = 1` means readmitted within 30 days and `readmitted = 0` means not readmitted within 30 days. The total row count is not the same as the number of unique patients or encounters.

## 4. Tools and Technologies

- **Microsoft Excel** — data exploration, calculations, and dashboard creation.
- **Excel Tables and structured references** — working with dataset fields and formulas.
- **PivotTables** — summarizing readmission proportions, average length of stay, and group-level measures.
- **PivotCharts** — presenting comparisons across categories.
- **Excel formulas** — including `AVERAGE`, `COUNTA`, and `CORREL` where applicable.
- **Data grouping and sorting** — grouping age ranges and ranking specialties.
- **Power Query** — unpivoting medication indicator columns for the medication-status analysis.
- **Dashboard design** — KPI cards, chart titles, labels, formatting, and layout.

## 5. Dashboard

<img width="1630" height="658" alt="image" src="https://github.com/user-attachments/assets/a8e5e0f8-dde7-4867-8278-d932662ada4b" />


The dashboard contains four KPI cards and visualizations covering:

- Readmission by weight range
- Readmission rate by age and gender
- Readmission by age group
- Average length of stay for the top 10 specialties
- Readmission by medication-change status
- Readmission status by diabetes-medication status

## 6. Analysis Results and Insights

### Basic-level analysis

1. **Age and readmission:** Readmission proportions vary across age groups. The dashboard shows approximately 22.0% for `[0–10)`, 48.0% for `[70–80)`, and 48.3% for `[80–90)`. These are descriptive comparisons.
2. **Specialty and length of stay:** Among the specialties shown in the dashboard, Pediatrics-Pulmonology has the highest displayed average stay at approximately 11.00 days. Physical Medicine and Rehabilitation is approximately 8.91 days, and Rheumatology is approximately 8.44 days.
3. **Emergency visits and readmission:** Correlation between `number_emergency` and `readmitted` is approximately **0.10782**, a weak positive association.
4. **Diabetes medication and readmission:** The displayed readmission proportion is approximately **47.96%** for `diabetesMed = Yes` and **40.34%** for `No`, a difference of **7.62 percentage points**. This does not show that medication causes readmission.
5. **Medication change and readmission:** The previously calculated difference between the `change` groups was approximately **4.49 percentage points**. This is descriptive; statistical significance was not tested.
6. **Lab procedures and readmission:** Correlation between `num_lab_procedures` and `readmitted` is approximately **0.03569**, a very weak positive association.
7. **Race, gender, and readmission:** A PivotTable compared average readmission proportions across race and gender groups. Group differences should be interpreted cautiously and in the context of group sizes and other factors not captured in the data.
8. **Weight and readmission:** The chart shows different proportions across recorded weight ranges, but approximately 97% of weight values are missing. The displayed 100% for `>200` may also reflect a small group, so the chart should not be used to draw strong conclusions.
9. **Medication count and length of stay:** Correlation between `num_medications` and `time_in_hospital` is approximately **0.46602**, a moderate positive association.
10. **Outpatient visits and readmission:** Correlation between `number_outpatient` and `readmitted` is approximately **0.08159**, a very weak positive association.

### Medium-level analysis

- **Time trends:** Not answerable because a suitable encounter date/time field is unavailable.
- **Number of diagnoses:** Correlation with length of stay is approximately **0.21789** and with `readmitted` approximately **0.10726**. These are weak and very weak positive associations, respectively.
- **Discharge disposition:** Not answerable because the required field is unavailable.
- **Demographics and care activity:** The displayed average number of lab procedures by race is approximately 44.11 for African American, 41.37 for Asian, 42.86 for Caucasian, 41.73 for Hispanic, 43.83 for Other, and 44.52 for unknown race. These are descriptive group averages, not causal findings.
- **Primary diagnosis and previous utilization:** The analysis compares average inpatient, outpatient, and emergency visits by `diag_1`. Exact top-category values were not retained, so no specific highest diagnosis is claimed here.
- **Medication indicators by specialty/readmission:** Medication fields were unpivoted and summarized in PivotTables. The status labels differ between medication indicators, so comparisons are exploratory and do not measure medication effectiveness.
- **Weight, primary diagnosis, and readmission:** A combined PivotTable was explored, but the high level of missing weight data limits conclusions.
- **Diabetes-medication subgroup:** Records with `diabetesMed = Yes` were compared across available medication indicators/statuses. Exact group-level rates were not retained, and the results cannot establish treatment effectiveness.
- **Patient satisfaction:** Not answerable because satisfaction or survey data are unavailable.

### Advanced scope decisions

- **Predictive readmission model:** Intentionally excluded. This project is a descriptive Excel analysis and does not train or evaluate a predictive model.
- **Patient utilization segmentation:** A patient-level summary of inpatient, outpatient, and emergency visits alongside readmission was prepared, but a completed segmentation scheme and validated segment conclusions were not retained. It is therefore treated as exploratory rather than a finished result.
- **Financial impact:** Not answerable because cost data and preventability criteria are unavailable.
- **Social determinants:** Race, gender, and age can be explored, but income, education, housing, and other social-risk fields are unavailable. This is not a complete social-determinants assessment.
- **Post-discharge program impact:** Cannot be measured because program participation and follow-up outcomes are unavailable.

## 7. Challenges Faced

- **Missing data:** The weight field is missing for approximately 97% of records, limiting weight-based analysis.
- **Dataset structure and counts:** Total rows, unique patients, and unique encounters are different measures. Counts must be labeled carefully to avoid treating records as unique patients.
- **Large dataset handling:** The source file is large, and medication-indicator analysis required reshaping data rather than using the original wide layout directly.
- **Unavailable fields:** The dataset does not contain information needed for time trends, discharge disposition, satisfaction, long-term outcomes, or costs.
- **Chart readability:** Many categories can make PivotCharts crowded; grouping categories, ranking specialties, and using clear titles and labels helps.
- **Interpretation:** Correlation and differences between groups do not establish causation, and rates from small groups can be unstable.

## 8. Recommendations for Hospital Process Improvement

These are **suggestions for further investigation**, not proven interventions from this dataset:

1. **Review high-readmission groups:** Examine the care pathways and patient characteristics behind groups with higher observed readmission proportions, especially before deciding on targeted interventions.
2. **Review medication reconciliation and discharge planning:** Consider auditing whether medication lists, discharge instructions, and follow-up plans are consistently completed. The dataset alone cannot prove that medication status causes readmission.
3. **Investigate prior utilization:** Use prior inpatient and emergency visits as possible flags for a closer case review, rather than treating them as causal predictors.
4. **Review long-stay specialties:** Work with specialty teams to understand operational factors behind longer average stays, while accounting for case complexity and patient mix.
5. **Improve data completeness:** Capture weight consistently when clinically appropriate, and document missingness reasons. Add encounter dates, discharge disposition, follow-up completion, patient satisfaction, and cost fields if future analyses need to cover those questions.
6. **Track follow-up metrics in future work:** If a follow-up program is introduced, monitor 30-day readmission, follow-up completion, medication-review completion, and time to follow-up before and after implementation, using a suitable evaluation design.
7. **Validate findings before acting:** Check group sizes, compare results across relevant subgroups, and seek clinical/operational review before making policy decisions.


## 9. Conclusion

The analysis found an overall readmission proportion of approximately **46.20%** and an average length of stay of approximately **4.40 days**. The diabetes-medication groups have different observed readmission proportions, and medication count has a moderate positive association with length of stay. Several other correlations with readmission are weak or very weak. The findings can guide further questions for hospital teams, but missing data and absent operational fields limit the conclusions that can be drawn.

## Repository Files

- `README.md` — project overview, methods, findings, challenges, and recommendations.
- `images/hospital-readmission-dashboard.png` — dashboard screenshot.
- Excel workbook link — source analysis and dashboard/
