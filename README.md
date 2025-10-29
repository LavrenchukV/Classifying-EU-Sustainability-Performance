# Socioeconomic Performance Grouping (SPG) — Machine Learning Analysis

## Overview
This project analyzes socioeconomic indicators across countries to classify them into performance tiers.  
It combines exploratory data analysis (EDA), feature engineering, and supervised machine learning to derive interpretable insights and policy implications.

The complete analysis is documented in the Jupyter notebook **`SPG_project_Final.ipynb`**.

---

## Data Exploration
A comprehensive exploratory data analysis was performed using **pandas**, **numpy**, **matplotlib**, and **seaborn**.  
Key steps included:

- Assessing missing values and variable distributions.  
- Identifying and handling outliers.  
- Imputing missing data using **subregion-level averages**, which proved more reliable than country-based imputation.  
- Exploring relationships between variables using correlation plots and pairwise visualizations.

### Example Figures
![Correlation_of_performance_tier_with_other_variables](plots/Correlation.png)  

---

## Machine Learning Task
A complete ML pipeline was implemented with a focus on interpretability and robustness.

**Pipeline Components**
- Feature preprocessing (scaling, encoding, imputation)
- Model training: Logistic Regression (with regularization), Random Forest
- Hyperparameter tuning via grid/randomized search
- Cross-validation and performance evaluation

## Results and Insights
### Tier Characterization Table
| Category | Tier 0 – "Needs Improvement" | Tier 1 – "Good" | Tier 2 – "Leaders" |
|----------|-------------------------------|-----------------|--------------------|
| **Institutional quality and governance** | High corruption, low press freedom, high crime → weak institutions. | Moderate corruption and governance; uneven progress in press freedom and safety. | Low corruption, strong rule of law, free press, safe environments. |
| **Economic structure and innovation** | Low income (€9k–15k PPP), minimal R&D (<0.5% GDP), high unemployment (>15%). | Middle-income (€15k–25k), moderate R&D (0.5–1.5%), unemployment 7–15%. | High income (>€25k), high R&D (>2%), low unemployment (<7%). |
| **Human capital and social inclusion** | Low digital skills (<40%), weak adult training (<10%), tertiary education <30%, large gender gaps (>20 pp). | Digital skills 50–65%, adult training 10–20%, tertiary education 30–45%, gender gap 10–20 pp. | High digital skills (>65%), adult training >20%, tertiary education >45%, gender gap <10 pp. |
| **Inequality and social balance** | High income inequality (Gini 35–45). | Moderate inequality (Gini 30–35). | Low inequality (Gini 22–30). |
| **Infrastructure and digitalization** | Broadband <70%. | Broadband 70–90%. | Broadband >90%. |
| **Environmental sustainability** | Low renewables (<20%), high CO₂ emissions (8–16 t). | Renewables 20–40%, CO₂ 6–10 t. | Renewables >40%, CO₂ 3–6 t. |
| **Distribution shapes (KDE insights)** | Peaks left for positive indicators, right/up for negatives. | Broader, sometimes bimodal peaks → heterogeneity within the group. Bimodality (R&D, adult training, gender gap, tertiary education, CO₂) shows Tier 1 is split into two subgroups: one closer to Tier 2, another leaning back toward Tier 0. | Clear right-shifts for positives, left-shifts for negatives → consolidated leaders. |
| **SDG Index** | • SDGI range: 55–65 <br> •  Сountries with significant gaps in achieving the SDGs | • SDGI range: 65–75 (peak at 70–72) <br> • Stable middle-level progress | • SDGI range: 75–82 <br> • Leaders, close to achieving most SDGs |
| **Economic interpretation** | Economies stuck in a development trap: weak institutions, low income, high inequality, poor innovation, high ecological footprint. | Economies at a crossroads: some advancing toward innovation and inclusion, others stagnating — explaining the bimodal distributions. | Economies with consolidated leadership: strong institutions, high innovation, inclusive labor markets, low inequality, and sustainable ecological policies. |
| **Summary** | Structurally constrained, high-risk economies. | Heterogeneous transitional group, with both “catch-up” and “lagging” trajectories. | Consolidated leaders combining prosperity, innovation, social inclusion, and sustainability. |


## Temporal and Regional Analysis
A separate analysis compared performance trends across **regions and performance tiers** over time,  
revealing shifts in socioeconomic patterns and development clusters.

![Regional Performance Trends](plots/SDGI_score_2015_2024.png)  
*Regional dynamics across observed periods.*

---

## Repository Structure

SPG_project_Final.ipynb # Main Jupyter notebook with analysis
data/ # Input data files
plots/ # Saved figures for README and publication
models/ # Trained model files (optional)
README.md # Project documentation

---

## Use Case and Policy Implications
This project demonstrates how an ML pipeline can be translated into a meaningful **use case** for socioeconomic analysis.  
Results can inform:
- Regional development strategies  
- Policy prioritization based on performance tiers  
- Benchmarking and progress tracking for international programs

---

## Technical Stack
- **Python**: pandas, numpy, matplotlib, seaborn, scikit-learn
- **Environment**: Jupyter Notebook  
- **Version Control**: Git & GitHub  

---

## Author
**Valentyna Lavrenchuk**  
Contact: lavrenchuk.v.an@gmail.com  
Affiliation: Kiron Open Higher Education / Thrive / Applied AI upskilling program
