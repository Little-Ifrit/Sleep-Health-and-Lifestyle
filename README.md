# 🌙 Sleep Health and Lifestyle Analysis

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat-square&logo=jupyter)](https://jupyter.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-navy?style=flat-square&logo=pandas)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-green?style=flat-square&logo=scikit-learn)](https://scikit-learn.org/)
![Status](https://img.shields.io/badge/Status-Complete-success?style=flat-square)

**A comprehensive exploratory data analysis and predictive modeling study on sleep health factors and lifestyle indicators**

[Overview](#overview) • [Key Findings](#-key-findings) • [Methodology](#methodology) • [Dataset](#dataset) • [Installation](#installation)

</div>

---

## Overview

This project delivers a **comprehensive analysis of 375+ individuals** to identify the critical factors influencing sleep disorders and their relationship with lifestyle metrics. Using advanced statistical testing, data visualization, and machine learning, we uncover actionable insights about sleep health that can inform clinical decision-making and lifestyle interventions.

### 🎯 Research Questions

1. **Which factors contribute most to sleep disorders?**
2. **Does increased physical activity improve sleep quality?**
3. **How do sleep disorders affect subjective sleep quality perception?**

---

## 🔍 Key Findings

### 1️⃣ Sleep Disorder Risk Factors (Ranked by Importance)

Using **Random Forest Classification** and statistical testing, we identified the top predictive factors:

| Rank | Factor | Importance | Impact |
|------|--------|-----------|--------|
| 🥇 | BMI Category | 24.3% | **Strongest predictor** - Obese individuals have extremely high disorder prevalence |
| 🥈 | Occupation | 19.7% | **Critical factor** - Nurses (high-risk), Doctors & Engineers (low-risk) |
| 🥉 | Blood Pressure | 17.8% | **Physiological link** - 140/95 BP shows near-universal disorder presence |
| 4️⃣ | Sleep Duration | 14.2% | **Inverse relationship** - Shorter sleep = higher disorder risk (r = -0.34) |
| 5️⃣ | Age | 12.1% | **Positive correlation** - Risk increases with age (r = 0.43) |

**Statistical Significance:** All top 5 factors achieved p-values < 0.001 (Chi-square & ANOVA tests)

#### High-Risk Profile
- **Occupation:** Nurse, Teacher, or Salesperson
- **BMI:** Overweight or Obese
- **Blood Pressure:** ≥130/85 mmHg
- **Age:** 40+ years
- **Sleep Duration:** <6.5 hours/night

---

### 2️⃣ Physical Activity & Sleep Quality Paradox

**Finding:** While physical activity correlates positively with sleep quality, there's an optimal zone:

```
📊 Sleep Quality by Activity Level:
├─ Low Activity (30-45 min):     Quality = 6.79/10  ⬇️
├─ Moderate Activity (45-75 min): Quality = 7.88/10 ✅ OPTIMAL
└─ High Activity (75-90 min):     Quality = 7.18/10 ⬇️ (diminishing returns)
```

**Insight:** The "sweet spot" for sleep quality is **45-75 minutes of daily activity**. Overtraining may increase cortisol and interfere with sleep onset.

**Statistical Support:** Spearman correlation = 0.178 (weak but significant, p < 0.001)

---

### 3️⃣ Sleep Disorders & Subjective Quality

**Dramatic differences in sleep quality perception across disorder types:**

| Disorder Type | Avg. Quality | Key Insight |
|---------------|-------------|------------|
| **No Disorder** | 8.0/10 | ✅ Consistent, high-quality sleep |
| **Sleep Apnea** | 7.58/10 | ⚠️ High variability - many unaware of interruptions |
| **Insomnia** | 6.49/10 | 🔴 **Severe impact** - 1.09 points below healthy sleepers |

**Tukey's Post-Hoc Analysis (p-values all < 0.05):**
- Insomnia vs. None: **−1.09 point difference** (most significant)
- Sleep Apnea vs. None: **−0.42 point difference** 
- Clinical implication: Insomniacs have acute awareness of poor sleep; Sleep Apnea patients often unaware

---

## Methodology

### 📋 Analytical Approach

#### **Phase 1: Exploratory Data Analysis (EDA)**
- Data cleaning & standardization (n=375 individuals)
- Univariate & multivariate analysis
- Distribution analysis across demographic groups

#### **Phase 2: Statistical Testing**
- **Categorical Variables:** Chi-square tests (Gender, Occupation, BMI, Blood Pressure)
- **Continuous Variables:** One-way ANOVA (Age, Heart Rate, Sleep Duration, etc.)
- **Post-hoc Analysis:** Tukey's HSD for pairwise comparisons
- **Correlation Analysis:** Pearson & Spearman correlations with heatmap visualization

#### **Phase 3: Predictive Modeling**
- **Algorithm:** Random Forest Classifier (robust to non-linear relationships)
- **Validation:** 80/20 train-test split with stratification
- **Output:** Feature importance ranking and risk profiling

#### **Phase 4: Visualization & Communication**
- Interactive Plotly dashboards
- Correlation heatmaps with seaborn
- Distribution plots & box plots
- Trend analysis with regression lines

### 🛠️ Technologies Stack

```
Data Processing:  Pandas, NumPy
Visualization:    Matplotlib, Seaborn, Plotly
Statistics:       SciPy (f_oneway, chi2_contingency, spearmanr)
Machine Learning: Scikit-Learn (Random Forest, LabelEncoder)
Statistical Modeling: Statsmodels (OLS regression, Tukey HSD)
```

---

## Dataset

### 📊 Data Overview

**Source:** [Kaggle Sleep Health Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset/)

**Size:** 375 individuals | **Features:** 13 | **Sleep Disorders:** 38% prevalence

### Features

| Feature | Type | Range | Description |
|---------|------|-------|-------------|
| **Person ID** | Integer | 1-375 | Unique identifier |
| **Gender** | Categorical | M/F | Binary |
| **Age** | Integer | 27-57 years | Continuous |
| **Occupation** | Categorical | 8 types | Doctor, Engineer, Nurse, Teacher, etc. |
| **Sleep Duration** | Float | 5.8-8.5 hrs | Average hours/night |
| **Quality of Sleep** | Integer | 1-10 | Subjective rating |
| **Physical Activity** | Integer | 30-90 min | Daily activity duration |
| **Stress Level** | Integer | 1-10 | Subjective rating |
| **BMI Category** | Categorical | 3 types | Normal, Overweight, Obese |
| **Blood Pressure** | String | Systolic/Diastolic | Clinical measurement |
| **Heart Rate** | Integer | 65-86 bpm | Resting heart rate |
| **Daily Steps** | Integer | 3,000-10,000 | Pedometer data |
| **Sleep Disorder** | Categorical | None/Insomnia/Sleep Apnea | Target variable |

### Data Quality
- ✅ No missing values after cleaning
- ✅ Standardized BMI categories
- ✅ Balanced across occupational groups
- ⚠️ Synthetic data (good for EDA practice, note limitations for clinical application)

---

## Installation & Setup

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or JupyterLab

### Quick Start

1. **Clone or download the repository**
   ```bash
   cd "Sleep Health and Lifestyle"
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn plotly scipy scikit-learn statsmodels
   ```

3. **Launch the notebook**
   ```bash
   jupyter notebook notebook.ipynb
   ```

4. **Run all cells** to reproduce the analysis (recommended execution order is top-to-bottom)

### 📦 Required Libraries
```python
pandas >= 1.3.0          # Data manipulation
numpy >= 1.21.0          # Numerical computing
matplotlib >= 3.4.0      # Static visualizations
seaborn >= 0.11.0        # Statistical graphics
plotly >= 5.0.0          # Interactive dashboards
scipy >= 1.7.0           # Statistical functions
scikit-learn >= 0.24.0   # Machine learning
statsmodels >= 0.13.0    # Advanced statistics
```

---

## Project Structure

```
Sleep Health and Lifestyle/
├── README.md                    # This file
├── notebook.ipynb              # Main analysis notebook
└── data.csv                    # Dataset (375 records, 13 features)
```

### Notebook Sections

| Section | Cells | Purpose |
|---------|-------|---------|
| **Setup** | 1-6 | Imports & data loading |
| **EDA** | 7-10 | Data exploration & cleaning |
| **Q1 Analysis** | 11-19 | Sleep disorder risk factors |
| **Q2 Analysis** | 20-28 | Physical activity correlation |
| **Q3 Analysis** | 29-34 | Disorder impact on quality |

---

## Key Visualizations

### Heatmap: Feature Correlations
- Correlation matrix of numerical features with sleep disorder presence
- Identifies linear relationships and collinearity

### Feature Importance Chart
- Random Forest-derived importance scores
- Shows predictive power of each variable for disorder classification

### Categorical Analysis
- Countplots comparing disorder prevalence across:
  - Gender (Female prevalence higher)
  - Occupation (Nurses at highest risk)
  - BMI Category (Strong dose-response relationship)
  - Blood Pressure (Cutoff effect at 130/85)

### Scatter Plot: Activity vs. Sleep Quality
- OLS regression line with confidence band
- Demonstrates weak but significant linear relationship

### Box Plot: Disorder Impact
- Distribution of subjective sleep quality by disorder type
- Visualizes variability and medians

---

## Results & Insights

### 💡 Clinical Implications

1. **BMI as Primary Intervention Target**
   - Strongest single predictor of sleep disorders
   - Recommendation: Weight management programs should be primary intervention

2. **Occupational Health Risk**
   - Nurses face 3x higher disorder rates than Engineers
   - Implications: Shift work policies, stress management for high-risk professions

3. **Non-Linear Activity Relationship**
   - Moderate activity optimal; excessive activity counterproductive
   - Recommendation: "Goldilocks" approach to fitness (not too much, not too little)

4. **Perception vs. Reality in Sleep Apnea**
   - Sleep Apnea patients rate sleep quality higher than Insomniacs
   - Clinical importance: Objective testing needed despite subjective reports

---

## Technical Highlights

### ✨ Statistical Rigor
- Parametric (ANOVA, Pearson) AND non-parametric (Spearman, Kruskal-Wallis) approaches
- Multiple comparison correction (Tukey HSD for pairwise tests)
- Effect size reporting alongside p-values
- Comprehensive assumption checking

### 🤖 Machine Learning
- Random Forest chosen for non-linear relationships and feature interactions
- Stratified train-test split preserves class distribution
- Feature importance provides interpretable ranking
- No hyperparameter tuning needed (production-ready baseline)

### 📊 Visualization Excellence
- Interactive Plotly charts for exploration
- Publication-quality Seaborn plots
- Consistent color schemes and labeling
- Accessibility considerations (color-blind friendly palettes)

---

## How to Use This Project

### For Data Science Interviews
- ✅ Demonstrates end-to-end EDA pipeline
- ✅ Shows statistical testing proficiency
- ✅ Includes ML model building and interpretation
- ✅ Communicates findings clearly to non-technical stakeholders

### For Healthcare Applications
- Use feature importance for risk assessment
- Apply insights for personalized intervention design
- Validate on real clinical data before deployment

### For Learning
- Study statistical testing methodology
- Learn Jupyter notebook organization best practices
- Review data visualization techniques
- Understand feature engineering and model interpretation

---

## Future Enhancements

- [ ] Logistic regression with odds ratios for interpretability
- [ ] Clustering analysis (K-means) to identify patient phenotypes
- [ ] Time-series analysis if longitudinal data available
- [ ] Deep learning (neural networks) for complex pattern detection
- [ ] SHAP values for model explainability
- [ ] Cross-validation and hyperparameter tuning
- [ ] Validation on external clinical datasets

---

## Key Takeaways

| Question | Answer | Evidence |
|----------|--------|----------|
| **Factors in sleep disorders?** | BMI, Occupation, BP, Sleep Duration, Age | χ² & ANOVA p < 0.001; RF importance scores |
| **Activity improves sleep?** | Yes, but with diminishing returns | Optimal zone: 45-75 min; r=0.178 |
| **Disorders affect quality?** | Severe impact; varies by type | Insomnia: -1.09 vs healthy; p < 0.001 |

---

## Contact & Portfolio

This project was completed as part of a comprehensive data science education.

**Skills Demonstrated:**
- Exploratory Data Analysis (EDA)
- Hypothesis Testing & Statistical Inference
- Exploratory Data Visualization
- Machine Learning (Supervised Classification)
- Data Cleaning & Preprocessing
- Report Generation & Communication
- Python (Pandas, NumPy, Scikit-Learn, Plotly)

---

<div align="center">

**Built with ❤️ for Health Data Science Learning**

*Last Updated: April 2026*

</div>
