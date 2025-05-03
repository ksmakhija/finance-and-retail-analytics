Company Default Prediction Using Financial Data
📌 Objective
This project is focused on building a Financial Health Assessment Tool to assist venture capitalists in evaluating companies' creditworthiness and financial well-being using historical balance sheet metrics. The tool supports:

Debt Management Analysis: Understand trends and detect risky financial behaviors.

Credit Risk Evaluation: Assess credit risk using key financial ratios.

The end goal is to predict whether a company is likely to default in the following year based on its financial indicators.

📊 Dataset Overview
The dataset, Comp_Fin_Data.csv, contains historical financial metrics for various companies, including:

Net worth, assets, liabilities

Profitability and turnover ratios

Cash flow and liquidity indicators

Ratios like Debt-to-Equity, Current Ratio, etc.

The target variable is Default, derived from Networth_Next_Year:

If Networth_Next_Year > 0 → Default = 0 (Non-defaulter)

If Networth_Next_Year ≤ 0 → Default = 1 (Defaulter)

📁 Project Structure
plaintext
Copy
Edit
├── data/
│   └── Comp_Fin_Data.csv
├── notebook/
│   └── company_default_analysis.ipynb
├── README.md
└── requirements.txt
⚙️ Methodology
1. Data Preprocessing
Cleaned column names (removed spaces, special chars).

Dropped irrelevant or heavily missing columns (>30% NA).

Handled outliers using IQR method.

Imputed missing values using KNN imputation.

2. Feature Engineering
Created target variable Default.

Scaled numerical features using StandardScaler.

Handled class imbalance using SMOTE oversampling.

3. Exploratory Data Analysis
Univariate distribution with histograms and boxplots.

Correlation heatmaps to identify multicollinearity.

4. Modeling
Baseline Model: Logistic Regression with Recursive Feature Elimination (RFE).

Evaluation Metrics: Accuracy, Recall, Precision, F1-score.

Handling Imbalance: SMOTE significantly improved recall score for the minority class (defaults).

📈 Results
After SMOTE balancing:

Improved recall for defaulters (minority class).

Maintained a good precision-recall balance.

Feature selection highlighted the most influential predictors.

🧪 Requirements
Install the dependencies with:

bash
Copy
Edit
pip install -r requirements.txt
Main Libraries
pandas, numpy, seaborn, matplotlib

scikit-learn

imbalanced-learn

statsmodels

🧠 Key Learnings
Class imbalance and missing data are critical challenges in credit risk modeling.

SMOTE can help build more sensitive models to minority classes.

Good feature engineering (cleaning, imputing, scaling) is crucial before modeling.

🚀 Future Enhancements
Try other robust models like XGBoost, Random Forests, or ensemble methods.

Use feature selection techniques like Lasso or Boruta.

Build an interactive dashboard for stakeholders using Streamlit or Dash.

📬 Contact
For feedback or contributions, please reach out to the project maintainer.

