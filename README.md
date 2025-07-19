#Exploring Global Respiratory Disease Burden and PM2.5 Pollution

This project analyzes the relationship between ambient PM2.5 pollution and the burden of respiratory diseases (measured by DALYs), with a focus on the role of income levels and urbanization across countries.

##Data Sources
PM2.5 Concentration (2024): World Population Review

DALYs due to Respiratory Diseases (2021): WHO

GDP per capita, PPP (2023): World Bank

Urban Population (% of total, 2023): World Bank

All variables are country-level aggregates. The outcome variable is DALYs from respiratory diseases, making this a respiratory-specific analysis.

##Project Objectives
Quantify the impact of PM2.5 on respiratory disease burden globally

Investigate how this relationship is moderated by economic development (GDP) and urbanization

Build predictive models using linear regression, Ridge, Lasso, and Random Forest

Explore feature engineering with interaction and polynomial terms

##Methodology
Data Cleaning & Merging: Combined multiple global datasets into a single DataFrame

Exploratory Analysis: Identified key patterns in pollution, income, urbanization, and health burden

Regression Analysis: Included interaction terms (PM2.5 × GDP, PM2.5 × Urban)

Regularization: Used Ridge and Lasso to assess model robustness and address multicollinearity

Model Comparison: Evaluated across raw, log-transformed, interaction, and polynomial feature sets

##Key Findings
Simple linear models performed poorly (R² < 0.1), indicating underfitting

Adding interaction terms improved explanatory power (R² ~ 0.23 with linear models)

Random Forest showed slight improvements but still underperformed due to limited features

Lasso tended to zero out weaker variables; Ridge retained most coefficients

Overall, PM2.5’s effect on respiratory DALYs is more pronounced in low-GDP and highly urbanized regions

##Results Summary
Feature Set	Best R² (Test)	Model
Raw Variables	0.121	Random Forest
Log-Transformed	0.134	Random Forest
With Interactions	0.232	Linear
With Polynomials	0.188	Ridge

##Tech Stack
Python (Pandas, NumPy, Scikit-learn, Statsmodels, Matplotlib, Seaborn)

Jupyter Notebooks

Version control via Git

##Project Structure

 respiratory_dalys_analysis/
 ┣ 📜data/              # Cleaned & raw datasets
 ┣ 📜notebooks/         # Jupyter analysis files
 ┣ 📜plots/             # Visual outputs
 ┣ 📜README.md
 ┗ 📜requirements.txt

##Future Directions
Incorporate satellite or regional pollution granularity

Explore non-linear models (XGBoost, GAMs)

Add education, healthcare access, and demographic variables

Time-series or panel data for dynamic analysis