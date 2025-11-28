# Hospital Patient Satisfaction Analysis

## Geographic Variation and Drivers of Hospital Patient Satisfaction: A Comprehensive Analysis of HCAHPS Survey Data Across US Hospitals (2023–2024)

---

## Project Overview

This project analyzes the Hospital Consumer Assessment of Healthcare Providers and Systems (HCAHPS) survey data to understand patient satisfaction patterns across US hospitals. Using over 442,000 records from the Centers for Medicare & Medicaid Services (CMS), this analysis explores geographic variation, identifies key drivers of patient satisfaction, and provides actionable insights for healthcare quality improvement.

---

## Objectives

1. **Quantify geographic variation** in patient experience by benchmarking HCAHPS survey results at the hospital, state, and national level
2. **Identify and model key drivers** (provider communication, environment, discharge planning) influencing patient satisfaction and recommendation rates
3. **Provide actionable insights** for healthcare systems using advanced statistical methods

---

## Data Source

| Attribute | Details |
|-----------|---------|
| **Source** | [CMS Provider Data Catalog](https://data.cms.gov/provider-data/dataset/dgck-syfz#overview) |
| **Dataset** | HCAHPS Inpatient Hospital Survey |
| **Records** | 442,215 observations |
| **Variables** | 22 columns |
| **Time Period** | October 2023 – September 2024 |
| **Coverage** | All 50 US states, DC, and US territories |

**Data Download:** [HCAHPS-Inpatient_Hospital_Survey.csv](https://american0-my.sharepoint.com/:x:/g/personal/wn8924a_american_edu/IQBiDeAy26TyS7HdDTWX-XvfAYiKrTMYdAx2Vd_qunp6R7c?e=rGU9Sa)

---

## Methods & Tools

### Technologies Used
- **R** (dplyr, tidyr, ggplot2, plotly)
- **Statistical Analysis**: Correlation analysis, multiple linear regression, cluster-robust standard errors
- **Visualization**: Interactive choropleth maps, heatmaps, diagnostic plots

### Analytical Steps
1. Data wrangling and cleaning
2. Transformation from long to wide format
3. Calculation of facility and state-level averages
4. Geographic mapping and visualization
5. Correlation analysis across patient experience domains
6. Multiple regression modeling with state-level adjustments
7. Cluster-robust inference for generalization

---

## Project Structure

```
├── README.md                           <- Project documentation
├── Portfolio-1.qmd                     <- Main Quarto analysis file
├── Portfolio-1.html                    <- Rendered HTML report
├── HCAHPS-Inpatient_Hospital_Survey.csv <- Raw data (hosted on OneDrive)
├── figures/                            <- Visualization outputs
│   ├── choropleth_map.png
│   ├── correlation_heatmap.png
│   ├── regression_diagnostics.png
│   └── ...
└── reports/                            <- Summary reports
```

---

## Key Findings

### National-Level Summary

| Metric | Min | Median | Mean | Max |
|--------|-----|--------|------|-----|
| Patient Survey Star Rating | 1.0 | 3.0 | 3.22 | 5.0 |
| HCAHPS Answer Percent | 0% | 23% | 34.71% | 100% |
| Survey Response Rate | 4% | 21% | 22.48% | 70% |

### State-Level Performance

**Top Performing States (Mean Star Rating):**
| State | Mean Star Rating |
|-------|------------------|
| Wisconsin (WI) | 3.89 |
| Nebraska (NE) | 3.86 |
| Minnesota (MN) | 3.84 |
| Iowa (IA) | 3.61 |

**Lower Performing States:**
| State | Mean Star Rating |
|-------|------------------|
| California (CA) | 2.80 |
| New York (NY) | 2.66 |
| District of Columbia (DC) | 2.32 |

### Geographic Distribution
---

![Mean Patient Survey Star Rating by State](https://github.com/weston-nyabeze/Hospital-Patient-Satisfaction/blob/main/USA%20Choropleth%20map.png)

---

## Correlation Analysis

Strong correlations (r = 0.75–0.96) were found among core patient experience domains:

| Domain Pair | Correlation |
|-------------|-------------|
| Nurse Communication & Nurse Respect | 0.95 |
| Doctor Communication & Doctor Respect | 0.95 |
| Call Button & Bath Help | 0.88 |
| Staff Communication & Discharge Info | 0.65 |

![Correlation Heatmap](https://github.com/weston-nyabeze/Hospital-Patient-Satisfaction/blob/main/patient_experience_correlations.png))

---

## Regression Results

### Model Performance
- **R²** = 0.687 (68.7% variance explained)
- **Adjusted R²** = 0.681
- **F-statistic** = 119.96 (p < 0.001)

### Key Predictors of "Definitely Recommend" Rate

| Predictor | Coefficient | Significance |
|-----------|-------------|--------------|
| Nurse Communication (H_COMP_1_A_P) | +0.572 | *** |
| Doctor Communication (H_COMP_2_A_P) | +0.221 | *** |
| Doctor Respect (H_DOCTOR_RESPECT_A_P) | +0.285 | *** |
| Medicine Explanation (H_MED_FOR_A_P) | +0.187 | *** |
| Quietness (H_QUIET_HSP_A_P) | +0.168 | *** |
| Discharge Help (H_DISCH_HELP_Y_P) | +0.233 | *** |
| Cleanliness (H_CLEAN_HSP_A_P) | +0.097 | *** |
| Mean Response Rate | +0.175 | *** |

*Significance: *** p < 0.01, ** p < 0.05, * p < 0.1*

### Regression Diagnostics

![Regression Diagnostic Plots](https://github.com/weston-nyabeze/Hospital-Patient-Satisfaction/blob/main/regression_diagnostics.png)

---

## Key Insights

1. **Communication is King**: Nurse and doctor communication are the strongest predictors of patient recommendations
2. **Environment Matters**: Hospital cleanliness and quietness independently affect patient perceptions
3. **Discharge Planning**: Clear discharge instructions significantly boost recommendation rates
4. **Regional Patterns**: Midwest states consistently outperform coastal urban centers
5. **Engagement Counts**: Higher survey response rates correlate with better satisfaction scores

---

## Recommendations

1. **Invest in Communication Training** for nurses and doctors—these domains have the strongest impact on recommendations
2. **Enhance Care Environment** by improving cleanliness and reducing noise levels
3. **Strengthen Discharge Planning** to ensure every patient receives clear post-hospital care instructions

---

## Limitations

- Structural missing data due to non-applicable survey questions
- Some territories (AS, GU, MP) excluded due to lack of valid responses
- Unmeasured confounders (demographics, resource levels) may affect findings
- Cross-sectional design limits causal inference

---

## Future Directions

- Incorporate hospital ownership, system membership, and socioeconomic profiles
- Apply hierarchical/multilevel modeling for deeper insights
- Conduct longitudinal tracking to assess changes over time
- Integrate qualitative patient feedback for nuanced interpretation

---

## Full Report

For the complete analysis with all code and visualizations, see the rendered report:
[HCAHPS_Patient_Satisfaction_Analysis_2024](https://github.com/weston-nyabeze/Hospital-Patient-Satisfaction/blob/main/HCAHPS_Patient_Satisfaction_Analysis_2024..pdf))

---

## Author

**Weston Nyabeze**

- 🎓 Education: American University
- 💼 Specialization: Healthcare Analytics
- 🔗 LinkedIn: [www.linkedin.com/in/weston-nyabeze](https://www.linkedin.com/in/weston-nyabeze)
  
---

## License

This project is licensed under the **MIT License**. See the [`LICENSE`](LICENSE) file for details.

---

## Acknowledgments

- **Centers for Medicare & Medicaid Services (CMS)** for providing the HCAHPS dataset
- **American University** for academic support
- **Perplexity AI** for research assistance, code development, and analytical guidance
