# MSDS 607 — Final Project: Predicting Onset of Diabetes (Pima Indians Dataset)

## Overview
This repository contains the final project for **MSDS 607**, developed by **Taha Malik**. The project predicts the onset of diabetes among Pima Indian women using machine learning models based on the Pima Indians dataset. The repository includes a reproducible data analysis workflow focusing on data cleaning, exploratory analysis, machine learning modeling, and model interpretation.

The project follows the **OSEMN** data science workflow:
1. **Obtain**: Dataset sourced from `diabetes.csv` and metadata from OpenML.
2. **Scrub**: Handle missing/invalid values, derive features, and perform imputation.
3. **Explore**: Visualize descriptive statistics and relationships.
4. **Model**: Logistic regression, Random Forest, and XGBoost models.
5. **Interpret**: Evaluate models using AUC, ROC, calibration curves, and SHAP explanations.

The project deliverables include the RMarkdown analysis, reports, plots, and code.

---

## Project Files and Structure
```
DATA607-FINAL/
├── data/
│   └── diabetes.csv           # Original dataset used in the analysis
├── R/
│   ├── proposal.Rmd           # Full RMarkdown analysis (provided file)
│   ├── final_report.Rmd       # Optional: Final extended version of the report
├── slides/                    # Slide deck for presentation (optional)
├── README.md                  # Documentation and setup instructions
├── requirements.R             # R script to install required packages
├── outputs/                   # Save plots, AUC tables, etc. here after running
└── LICENSE                    # License file for open-source use
```

---

## About the Dataset
- **Name:** Pima Indians Diabetes Dataset
- **Description:** The dataset contains diagnostic measurements for predicting diabetes risk among Pima Indian women.
- **Features:**
  - Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin
  - Body Mass Index (BMI), Age, DiabetesPedigreeFunction
- **Target Variable:** Outcome (1 = Diabetes, 0 = No Diabetes)

The dataset includes instances with missing or biologically implausible values for some predictors, such as zeros for Glucose and BMI. Appropriate cleaning and imputations are applied to mitigate missingness.

---

## Requirements

To reproduce the analysis, you need to install the following R packages:

### Install Packages
Use the following script to install all the required packages:

```R
# Uncomment the lines below to install necessary packages
# packages <- c("tidyverse", "caret", "pROC", "randomForest", "xgboost", "vip", 
#               "fastshap", "gridExtra", "mice", "corrplot", "skimr", "knitr", 
#               "kableExtra", "rmarkdown")
# install.packages(setdiff(packages, rownames(installed.packages())))
```

---

## How to Run:

1. Clone the Repository:
   ```bash
   git clone https://github.com/tahamalik80/DATA607-FINAL.git
   cd DATA607-FINAL
   ```

2. Add the dataset:
   Place the `diabetes.csv` file in the `data/` folder.

3. Ensure all required R packages are installed (see above).

4. Open the `proposal.Rmd` file in RStudio.

5. Knit the RMarkdown file to produce the analysis report:
   - The knitted output (HTML/PDF) includes all deliverables such as plots, tables, and interpretations of the models' results.
   - Make sure to set the working directory to the root of the repository.

---

## Project Deliverables
1. **Reproducible RMarkdown File (`proposal.Rmd`)**:
   - Includes the complete workflow with chunks for:
     - Data cleaning and imputation (simple median and multiple imputation methods)
     - Exploratory data analysis (EDA)
     - Predictive modeling using logistic regression, random forests, and XGBoost.
     - Model evaluation (AUC, ROC, calibration, etc.)
     - Interpretability analysis (SHAP, permutation importance).

2. **Knitted Report (HTML or PDF)**:
   - Includes all figures, tables, and explanations.
   - The document maps directly to the course rubric for maximum points.

3. **Presentation Slides**:
   - Optional: A deck summarizing the analysis and findings.

4. **Code and Data**:
   - Full R code and the `diabetes.csv` dataset for reproducibility.

---

## Results Summary

- **Best Model**: XGBoost
  - **Test AUC**: ~0.83
  - **Top Predictors**: Glucose, BMI, Age, Insulin

- **Key Insights**:
  - Higher glucose levels, BMI, and age were strongly associated with diabetes onset.
  - Tree-based models, such as Random Forest and XGBoost, outperformed logistic regression by capturing non-linear interactions and complex feature relationships.

- **Interpretation**:
  - SHAP values highlighted the most significant predictors and their direction of influence on individual predictions.
  - Calibration analysis showed reasonable agreement between predicted probabilities and observed outcomes in the best model.

---

## Known Issues and Limitations
- Dataset represents only female Pima Indians; generalizability to other populations is limited.
- Potential measurement errors for predictors like Insulin and SkinThickness.
- Models are predictive but cannot establish causal relationships.
- Missing value imputation introduces some uncertainty in predictions.

---

## Acknowledgments
- **Data Source:** Pima Indians Diabetes Dataset, available via OpenML (dataset id 37).
- **References:**
  - Smith et al. (1988) for the original paper.
  - American Diabetes Association for clinical context.

---

## License
This project is open source under the [MIT License](LICENSE). Feel free to use, modify, and distribute with attribution.

---

Happy Learning and Coding!
