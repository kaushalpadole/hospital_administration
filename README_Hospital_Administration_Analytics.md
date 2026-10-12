# Hospital Administration Analytics — Excel Case Study

## Project Overview
This project analyzes hospital encounter data in Excel to explore patterns associated with 30-day readmission and length of stay using PivotTables, PivotCharts, descriptive statistics, and correlation analysis. Findings are descriptive and do not establish causation.

## Dashboard
![Hospital Readmission Analysis Dashboard](images/hospital-readmission-dashboard.png)

## Dataset Summary

| Metric | Result |
|---|---:|
| Total rows / records | 66,587 |
| Unique patients | 39,650 |
| Overall readmission proportion | 46.20% |
| Average length of stay | 4.40 days |
| Weight field missing | Approximately 97% |

`readmitted = 1` represents readmission within 30 days; `readmitted = 0` represents no readmission within 30 days.

## Answers and Findings

### Basic Questions

**Q1. How does age relate to readmission?**  
Readmission proportions vary by age group. The dashboard shows approximately 22.0% for `[0–10)`, 48.0% for `[70–80)`, and 48.3% for `[80–90)`. These are descriptive differences, not proof that age alone determines readmission.

**Q2. Which specialties have the longest average hospital stays?**  
Among specialties displayed in the Top 10 chart, Pediatrics-Pulmonology is highest at approximately 11.00 days, followed by Physical Medicine and Rehabilitation at 8.91 days and Rheumatology at 8.44 days.

**Q3. Is emergency-visit history associated with readmission?**  
The correlation between `number_emergency` and `readmitted` is approximately **0.10782**, a weak positive association.

**Q4. Does readmission differ by diabetes-medication status?**  
Yes. The dashboard shows approximately **47.96%** readmission for `diabetesMed = Yes` and **40.34%** for `No`, a difference of **7.62 percentage points**. This association does not mean diabetes medication causes readmission.

**Q5. Does medication change relate to readmission?**  
The observed readmission-rate difference between `change` groups was approximately **4.49 percentage points**. This is descriptive; no statistical significance test was performed.

**Q6. Are more lab procedures associated with readmission?**  
The correlation between `num_lab_procedures` and `readmitted` is approximately **0.035691**, a very weak positive association.

**Q7. How do readmission proportions vary by race and gender?**  
The race-by-gender PivotTable shows variation across available groups. Interpret these differences descriptively, considering group sizes and other unmeasured factors.

**Q8. How does weight relate to readmission?**  
Observed proportions differ by weight range, but approximately **97% of weight values are missing**. The dashboard displays about 25.00% for `[150–175)` and 100.00% for `>200`; extensive missingness and potentially small groups make these results unreliable for strong conclusions.

**Q9. Is medication count associated with length of stay?**  
The correlation between `num_medications` and `time_in_hospital` is approximately **0.466018**, a moderate positive association.

**Q10. Are outpatient visits associated with readmission?**  
The correlation between `number_outpatient` and `readmitted` is approximately **0.08159**, a very weak positive association.

### Medium-Level Questions

**Q11. How does readmission change over time?**  
Not answerable: the dataset has no suitable encounter date/time field.

**Q12. Is number of diagnoses associated with length of stay and readmission?**  
`number_diagnoses` has a correlation of approximately **0.21789** with length of stay and **0.107257** with `readmitted`. Both are positive associations; the first is weak and the second very weak.

**Q13. How does discharge disposition affect readmission?**  
Not answerable because the required discharge-disposition field is unavailable.

**Q14. Do demographic groups differ in recorded care activity?**  
The displayed average lab procedures by race were approximately: African American **44.11**, Asian **41.37**, Caucasian **42.86**, Hispanic **41.73**, Other **43.83**, and unknown race **44.52**. These are group averages, not evidence that race causes differences in care.

**Q15. How does primary diagnosis relate to prior healthcare utilization?**  
The `diag_1` analysis compares average inpatient, outpatient, and emergency visit counts across diagnosis groups. Exact top-group values were not retained, so a specific highest diagnosis is not reported.

**Q16. What are long-term outcomes after discharge?**  
Not answerable because mortality, longitudinal follow-up, and post-discharge outcome data are unavailable.

**Q17. Do medication indicators differ by specialty and readmission status?**  
Medication-indicator fields were unpivoted and summarized by specialty and readmission status. This enables descriptive comparison, but status labels vary across indicators and should not be treated as a common scale or evidence of medication effectiveness.

**Q18. How do weight and primary diagnosis jointly relate to readmission?**  
A PivotTable compared average readmission proportion by weight category and `diag_1`. This is exploratory only because approximately 97% of weight values are missing.

**Q19. Among records marked as receiving diabetes medication, how do medication indicators relate to readmission?**  
The analysis filtered to `diabetesMed = Yes` and compared readmission proportions across medication indicator/status groups. Exact group-level rates were not retained; the comparison does not establish treatment effectiveness.

**Q20. How does patient satisfaction relate to readmission?**  
Not answerable because patient satisfaction or survey data are not included.

### Advanced Questions

**Q21. Predictive readmission model**  
Intentionally excluded. This project focuses on descriptive analysis in Excel and does not build or evaluate a predictive model.

**Q22. Can patients be segmented by prior healthcare utilization?**  
A patient-level summary was prepared using inpatient, outpatient, and emergency visit counts alongside average readmission. A completed segmentation scheme and validated segment-level conclusions were not retained, so this remains exploratory work.

**Q23. What is the financial impact of readmissions?**  
Not answerable because encounter costs and criteria for preventable readmissions are unavailable.

**Q24. Do available demographic factors relate to readmission?**  
The dataset supports exploratory comparisons by race, gender, and age. It lacks a full set of social determinants such as income, education, and housing, so it cannot provide a complete social-risk assessment.

**Q25. Did a post-discharge follow-up program reduce readmission?**  
The dataset cannot quantify program impact because it does not identify program participation and follow-up outcomes. No intervention effect is calculated.

## Main Conclusions

- Overall readmission proportion is approximately **46.20%**.
- The `diabetesMed = Yes` group has a higher observed readmission proportion than the `No` group (47.96% vs. 40.34%).
- Medication count has a moderate positive correlation with length of stay (**r ≈ 0.466**).
- Correlations between readmission and emergency visits, outpatient visits, lab procedures, and number of diagnoses are weak or very weak.
- Average length of stay varies by specialty; Pediatrics-Pulmonology is highest among specialties shown in the dashboard.
- Weight-based findings are especially uncertain because most weight values are missing.

## Limitations and Scope
Time trends, discharge disposition, long-term outcomes, patient satisfaction, financial impact, and intervention effectiveness cannot be answered because required fields are unavailable. The predictive-model question is intentionally excluded as outside the scope of this Excel descriptive-analysis project. Correlation and group differences do not establish causation.

## Tools Used
- Microsoft Excel
- PivotTables and PivotCharts
- Excel formulas including `AVERAGE` and `CORREL`
- Data grouping, sorting, descriptive analysis, KPI cards, and dashboard formatting

## Disclaimer
This is an educational analytics project, not a clinical decision-support system. It should not be used to make patient-care decisions.
