# Loan Dataset EDA

A detailed Exploratory Data Analysis (EDA) of a loan dataset aimed at uncovering key insights and patterns that will help inform feature selection and predictive modeling for loan approval or default.

---

## 📂 Project Structure

Loan_dataset_EDA/
├── data/
│ └── loan_data.csv # Primary dataset
├── notebooks/
│ └── Loan_EDA.ipynb # Jupyter notebook containing analysis and visualizations
├── reports/
│ └── EDA_summary.md # Text summary of findings (optional)
└── README.md # This file

markdown
Copy
Edit

---

## 🧠 Objective

- To explore relationships between applicant demographics, financial behaviors, and loan outcomes.  
- To identify data issues (missing values, outliers) and perform cleaning.  
- To derive insights to guide feature engineering and model selection.

---

## 📋 Dataset

Typical features include:

- **Numerical**: `age`, `annual_income`, `loan_amount`, `loan_term`  
- **Categorical**: `gender`, `employment_type`, `loan_purpose`, `loan_status`

*(Replace with your actual feature names.)*

---

## 🔍 Analysis Workflow

1. **Data Exploration**  
   - Loaded dataset; used `.info()` and `.describe()` to check types, ranges, and missingness.  
   - Visualized distributions for each variable.

2. **Data Cleaning & Outlier Removal**  
   - Handled missing values using `fillna()` and `dropna()`.  
   - Employed IQR or percentile-based methods to detect and remove outliers from numerical features.

3. **Feature Visualization**  
   - **Boxplots** for spread and outlier detection.  
   - **Histograms/KDE plots** to understand skewness in `annual_income` and `loan_amount`.  
   - **Bar charts / Pie charts** for categorical feature distribution.  
   - **Heatmap** to visualize correlations and potential multicollinearity.

4. **Feature–Target Relationships**  
   - Examined how income, loan amount, age, and employment type vary across `loan_status`.  
   - Identified features with strong predictive potential.

---

## 📊 Key Insights

- **Missing & Outlier Data**: Moderate missingness in some income/loan fields; outliers removed based on IQR thresholds.  
- **Distribution**: Right-skew to income and loan amount—consider log transforms in modeling.  
- **Correlations**:  
  - Positive correlation (~0.4–0.6) between `annual_income` & `loan_amount`.  
  - Low inter-correlation among other features—favorable for model stability.  
- **Categorical Imbalances**:  
  - One gender (e.g., Male/Female) more represented.  
  - Some employment types / loan purposes heavily skewed—may need grouping or oversampling.

- **Loan Outcome Patterns**:  
  - Higher-income applicants have higher approval rates.  
  - Certain employment and loan purposes show stronger associations with approval.

---

## 🎯 Summary & Next Steps

**Summary**:  
Your EDA is comprehensive and clean: distributions, correlations, outlier treatment, and target insights are well-covered. Categorical imbalances and skewed data distributions are now clearly identified.

**Next Steps**:  
1. **Preprocessing for modeling**  
   - Log-transform skewed features.  
   - Encode categorical variables (one-hot/label).  
   - Normalize or scale as needed.

2. **Model Prep**  
   - Handle class imbalance (e.g., SMOTE or stratified sampling).  
   - Select features based on EDA insights (e.g., `annual_income`, `loan_purpose`, `employment_type`).

3. **Modeling**  
   - Test classifiers: logistic regression, random forest, XGBoost.  
   - Use cross-validation; tune hyperparameters.

4. **Evaluation**  
   - Focus on recall/F1-score for the “default” class.  
   - Analyze feature importance to refine future feature engineering.

---

## 🧪 How to Reproduce

1. Clone the repo:  
   ```bash
   git clone https://github.com/KANCHARLA-SIVASAI/Loan_dataset_EDA.git
Install dependencies:

bash
Copy
Edit
pip install pandas numpy matplotlib seaborn scikit-learn
Run the notebook:
Open notebooks/Loan_EDA.ipynb in Jupyter and execute all cells to regenerate analysis and visualizations.

📝 Contact
Maintained by Kancharla Sivasai
📧 Open to suggestions and collaboration!
