# 📊 JAMB 2024 Performance Analysis
### Investigating Academic Performance Disparities Between Rural and Urban Students

---

## 📌 Key Findings

| Finding | Result |
|---------|--------|
| Urban vs Rural average score gap | 177.81 vs 174.91 (+2.9 points urban) |
| Statistical significance | p = 0.0564 — marginal, not conclusive at α = 0.05 |
| Strongest predictor of JAMB score | Teacher quality (+14.8 points per unit) |
| Assignment completion effect | +13.2 points — highest student-level predictor |
| Private vs Public school advantage | +10.7 points (rural context) |
| Parental tertiary education effect | +9.2 points |
| Distance to school effect | −0.27 points per distance unit |

---

## 📋 Project Overview

This project analyzes academic performance differences between **rural and urban 
students** using a sample of 2024 JAMB (Joint Admissions and Matriculation Board) 
examination data. Using statistical testing and linear regression modeling, the 
analysis identifies the root causes of performance gaps and provides evidence-based 
policy recommendations.

**Three core research questions:**
1. How do average JAMB scores of rural and urban students differ, and is the difference statistically significant?
2. What factors contribute to observed performance differences?
3. What strategies can each group adopt to strengthen academic outcomes?

---

## 🗂️ Project Structure

```
Jamb-2024-Performance-Analysis/
├── Project_Analysis.ipynb          ← Full analysis notebook (90 cells)
├── Powerpoint_presentation.pptx    ← Slide deck summary
├── Dataset/
│   └── jamb_exam_results.csv       ← 5,000 student records
└── README.md                       ← Project documentation
```

---

## 🔄 Methodology

### 1. Exploratory Data Analysis
- Dataset structure inspection (5,000 rows × 17 features)
- Class distribution across rural/urban groups
- Missing value analysis with proportional breakdown by region
- Skewness check to validate parametric test assumptions

### 2. Data Cleaning
- Dropped `Student_ID` (unique identifier, no analytical value)
- Investigated 891 missing `Parent_Education_Level` records
- Confirmed missingness balanced across regions (Rural: 45.8%, Urban: 54.2%)
- Applied listwise deletion without introducing systematic bias
- Treated outliers via **IQR-based Winsorization** (capping at Q1−1.5×IQR and Q3+1.5×IQR)
- Final working dataset: **4,109 students × 16 features**

### 3. Statistical Testing
- **Welch independent samples t-test** comparing rural vs urban JAMB means
- Appropriate for unequal group sizes and potentially unequal variances

### 4. Factor Analysis (Linear Regression Models)
Four categories of predictors modeled with interaction terms:

| Category | Factors Examined |
|----------|-----------------|
| I. Student-Related | Study hours, attendance rate, assignment completion, extra tutorials, access to materials |
| II. School-Related | Teacher quality, school type (public vs private) |
| III. Socioeconomic | Parental education, IT knowledge, parental involvement |
| IV. Environmental | Distance to school |

---

## 📊 Key Visualizations

| Visual | Insight |
|--------|---------|
| Regional distribution bar chart | Urban (57.2%) vs Rural (42.8%) sample split |
| Score threshold analysis | % of students above JAMB 200 cutoff by region |
| Study hours regression plot | Positive linear relationship with JAMB score |
| Outlier boxplots (pre/post) | Effect of winsorization on key variables |
| Coefficient importance chart | Ranked impact of socioeconomic predictors |
| Skewness histograms | Distributional validation across all numeric features |

---

## 🗃️ Dataset

- **Source:** Synthetic JAMB 2024 examination dataset
- **Original Size:** 5,000 students × 17 features
- **Working Size:** 4,109 students × 16 features

| Feature | Type | Description |
|---------|------|-------------|
| `JAMB_Score` | Continuous | Target variable — examination score |
| `Study_Hours_Per_Week` | Continuous | Weekly study hours |
| `Attendance_Rate` | Continuous | School attendance percentage |
| `Teacher_Quality` | Ordinal | Rated teacher effectiveness (1–5 scale) |
| `Distance_To_School` | Continuous | Distance from home to school |
| `School_Type` | Categorical | Public / Private |
| `School_Location` | Categorical | Rural / Urban — key grouping variable |
| `Extra_Tutorials` | Binary | Yes / No |
| `Access_To_Learning_Materials` | Binary | Yes / No |
| `Parent_Involvement` | Categorical | Low / Medium / High |
| `IT_Knowledge` | Categorical | Low / Medium / High |
| `Gender` | Categorical | Male / Female |
| `Age` | Continuous | Student age |
| `Socioeconomic_Status` | Categorical | Low / Medium / High |
| `Parent_Education_Level` | Categorical | Primary / Secondary / Tertiary |
| `Assignments_Completed` | Continuous | Number of assignments completed |

---

## 💡 Recommendations

**For Rural Schools & Policymakers:**
- Invest in teacher training and quality improvement — the highest-impact lever
- Provide transportation subsidies or boarding to reduce distance barriers
- Expand extra tutorial access — shown to add +6.7 points regardless of region

**For All Students:**
- Prioritize assignment completion (+13.2 points — strongest student-level predictor)
- Maintain high attendance (+1.3 points per 1% attendance increase)
- Build structured weekly study habits (+2.17 points per weekly hour)

---

## 🛠️ Tools & Libraries

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)

| Library | Purpose |
|---------|---------|
| `pandas / numpy` | Data manipulation and computation |
| `scipy.stats` | Welch t-test for group comparison |
| `scikit-learn` | Linear regression models |
| `matplotlib / seaborn` | Visualizations |

---

## ▶️ How to Reproduce

```bash
# 1. Clone the repository
git clone https://github.com/otene-daniel/Jamb-2024-Performance-Analysis.git
cd Jamb-2024-Performance-Analysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter

# 3. Launch the notebook
jupyter notebook Project_Analysis.ipynb
```

---

**Author:** Daniel Otene
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/otene-daniel)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR-LINKEDIN-URL)
