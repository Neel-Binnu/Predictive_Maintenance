# Predictive_Maintenance

# Predictive Maintenance for Oil & Gas Pipelines

## Overview
This project implements a **predictive maintenance solution** for oil and gas pipelines using classical machine learning techniques. The goal is to **predict maintenance requirements proactively** based on pipeline operational and material features, helping reduce downtime, maintenance costs, and operational risk.

---

## Dataset
The dataset includes operational, material, and condition metrics for pipelines:

- **Pipe Size**: Diameter of the pipeline  
- **Thickness**: Wall thickness of the pipe  
- **Material**: Type of material (e.g., steel, composite)  
- **Max_Pressure_psi**: Peak internal pressure (psi)  
- **Temperature_C**: Fluid temperature (°C)  
- **Corrosion_Impact_Percent**: Estimated corrosion level  
- **Thickness_Loss_mm**: Loss of wall thickness due to wear/corrosion  
- **Material_Loss_Percent**: Percentage of overall material loss  
- **Time_Years**: Age of the pipeline (years)  
- **Condition**: Operational category ('Normal', 'Moderate', 'Critical')  

The **target variable**,**Maintenance_Required**, was engineered based on:
- High damage readings (thickness loss, corrosion, material loss)  
- Pipe age and gradual degradation  
- Critical operational conditions, including young pipes under severe stress

---

## Methodology
1. **Exploratory Data Analysis (EDA)**  
   - Visualized distributions, correlations, and feature relationships  
   - Identified patterns and weak correlations (e.g., Time vs corrosion)

2. **Feature Engineering**  
   - Interaction features: 'time_thickness_interaction', 'time_corrosion_interaction'
   - Flag feature: 'young_critical' for young pipes under critical conditions  
   - Encoded categorical features for ML models

3. **Modeling**  
   - Built a **stacking ensemble** of classical classifiers:  
     - Random Forest  
     - Decision Tree  
     - Gradient Boosting  
     - Logistic Regression  
   - Meta-learner: Logistic Regression  
   - Trained using a **train/test split** with stratification

4. **Evaluation**  
   - Achieved **99% accuracy** on the test set  
   - Confusion matrix shows strong class separation  
   - Model outputs **maintenance probabilities** for risk ranking



