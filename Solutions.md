# Hospital Administration Analytics — Excel Case Study

## Answers and Findings

### Basic Questions

**Q1. How does age relate to readmission?**  
Readmission proportions vary by age group. The dashboard shows approximately 22.0% for `[0–10)`, 48.0% for `[70–80)`, and 48.3% for `[80–90)`. These are descriptive differences, not proof that age alone determines readmission.

<img width="551" height="276" alt="image" src="https://github.com/user-attachments/assets/e02b52b4-9c14-4e1f-9d83-7d4f6e5fc70f" />


**Q2. Which specialties have the longest average hospital stays?**  
Among specialties displayed in the Top 10 chart, Pediatrics-Pulmonology is highest at approximately 11.00 days, followed by Physical Medicine and Rehabilitation at 8.91 days and Rheumatology at 8.44 days.

<img width="608" height="255" alt="image" src="https://github.com/user-attachments/assets/3ececaa8-1e64-48b4-bc13-c8dcbeaf350b" />


**Q3. Is emergency-visit history associated with readmission?**  
The correlation between `number_emergency` and `readmitted` is approximately **0.10782**, a weak positive association.

<img width="557" height="182" alt="image" src="https://github.com/user-attachments/assets/94d97bff-4c66-45b3-83b4-5a93d872b564" />


**Q4. Does readmission differ by diabetes-medication status?**  
Yes. The dashboard shows approximately **47.96%** readmission for `diabetesMed = Yes` and **40.34%** for `No`, a difference of **7.62 percentage points**. This association does not mean diabetes medication causes readmission.

<img width="1082" height="158" alt="image" src="https://github.com/user-attachments/assets/62f22279-c7fe-488b-8595-a91991f4f8b3" />


**Q5. Does medication change relate to readmission?**  
The observed readmission-rate difference between `change` groups was approximately **4.49 percentage points**. This is descriptive; no statistical significance test was performed.

<img width="941" height="137" alt="image" src="https://github.com/user-attachments/assets/426d718d-1e09-488a-8a8e-96993496fab7" />


**Q6. Are more lab procedures associated with readmission?**  
The correlation between `num_lab_procedures` and `readmitted` is approximately **0.035691**, a very weak positive association.

<img width="852" height="552" alt="image" src="https://github.com/user-attachments/assets/2d387879-5026-44bd-affa-0dee2f833bb3" />


**Q7. How do readmission proportions vary by race and gender?**  
The race-by-gender PivotTable shows variation across available groups. Interpret these differences descriptively, considering group sizes and other unmeasured factors.

<img width="597" height="257" alt="image" src="https://github.com/user-attachments/assets/e6d3f33a-a3b6-4484-a14a-b87ce941d022" />


**Q8. How does weight relate to readmission?**  
Observed proportions differ by weight range, but approximately **97% of weight values are missing**. The dashboard displays about 25.00% for `[150–175)` and 100.00% for `>200`; extensive missingness and potentially small groups make these results unreliable for strong conclusions.

<img width="906" height="370" alt="image" src="https://github.com/user-attachments/assets/0b607499-5d65-41a3-abf1-096e900a8f1b" />


**Q9. Is medication count associated with length of stay?**  
The correlation between `num_medications` and `time_in_hospital` is approximately **0.466018**, a moderate positive association.
<img width="537" height="177" alt="image" src="https://github.com/user-attachments/assets/55c92392-290f-423c-a88d-aecf95f789f8" />


**Q10. Are outpatient visits associated with readmission?**  
The correlation between `number_outpatient` and `readmitted` is approximately **0.08159**, a very weak positive association.

<img width="533" height="192" alt="image" src="https://github.com/user-attachments/assets/4a48dc40-466b-499c-ad3e-80fe43fe3018" />


### Medium-Level Questions

**Q11. How does readmission change over time?**  
The dataset has no admission/discharge dates or month fields, so seasonal trends can't be built.

**Q12. Is number of diagnoses associated with length of stay and readmission?**  
`number_diagnoses` has a correlation of approximately **0.21789** with length of stay and **0.107257** with `readmitted`. Both are positive associations; the first is weak and the second very weak.

<img width="616" height="216" alt="image" src="https://github.com/user-attachments/assets/22437e61-f6fa-40e6-9a79-525d15542010" />


**Q13. How does discharge disposition affect readmission?**  
Not answerable because the required discharge-disposition field is unavailable.

**Q14. Do demographic groups differ in recorded care activity?**  
The displayed average lab procedures by race were approximately: African American **44.11**, Asian **41.37**, Caucasian **42.86**, Hispanic **41.73**, Other **43.83**, and unknown race **44.52**. 

<img width="742" height="216" alt="image" src="https://github.com/user-attachments/assets/b834db0e-6a23-4424-96cb-30de1875330f" />


**Q15. How does primary diagnosis relate to prior healthcare utilization?**  
The `diag_1` analysis compares average inpatient, outpatient, and emergency visit counts across diagnosis groups. Exact top-group values were not retained, so a specific highest diagnosis is not reported.

<img width="1047" height="646" alt="image" src="https://github.com/user-attachments/assets/c64e692a-e187-4a9f-8c0c-2bdba736a840" />


**Q16. What are long-term outcomes after discharge?**  
Not answerable because mortality, longitudinal follow-up, and post-discharge outcome data are unavailable.

**Q17. Do medication indicators differ by specialty and readmission status?**  
Medication-indicator fields were unpivoted and summarized by specialty and readmission status. This enables descriptive comparison, but status labels vary across indicators and should not be treated as a common scale or evidence of medication effectiveness.

<img width="1020" height="620" alt="image" src="https://github.com/user-attachments/assets/b241dfea-5b5d-41ea-9f00-8be26ea15c8c" />


**Q18. How do weight and primary diagnosis jointly relate to readmission?**  
A PivotTable compared average readmission proportion by weight category and `diag_1`. This is exploratory only because approximately 97% of weight values are missing.

<img width="356" height="243" alt="image" src="https://github.com/user-attachments/assets/d6f87614-6bce-4916-b7b4-a59aea9ac717" />


**Q19. Among records marked as receiving diabetes medication, how do medication indicators relate to readmission?**  
The analysis filtered to `diabetesMed = Yes` and compared readmission proportions across medication indicator/status groups. Exact group-level rates were not retained; the comparison does not establish treatment effectiveness.

<img width="405" height="601" alt="image" src="https://github.com/user-attachments/assets/a55cbafd-4b61-4bfd-a66d-ba1eba663b6c" />


**Q20. How does patient satisfaction relate to readmission?**  
Not answerable because patient satisfaction or survey data are not included.

### Advanced Questions

**Q21. Predictive readmission model**  
This project focuses on descriptive analysis in Excel and does not build or evaluate a predictive model.

**Q22. Can patients be segmented by prior healthcare utilization?**  
A patient-level summary was prepared using inpatient, outpatient, and emergency visit counts alongside average readmission. A completed segmentation scheme and validated segment-level conclusions were not retained, so this remains exploratory work.

<img width="1068" height="661" alt="image" src="https://github.com/user-attachments/assets/1aa8689b-2e9e-4330-96d5-cdea53068770" />


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
