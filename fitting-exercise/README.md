## Fitting Exercise

This exercise analyzes pharmacokinetic data for the drug candidate **Mavoglurant**. The goal is to explore the relationship between drug **dose** and **total drug exposure** using exploratory data analysis and simple statistical models in R.

The analysis includes:
- Data cleaning and preprocessing
- Exploratory data analysis (EDA)
- Linear regression models
- Logistic regression models
- A k-nearest neighbors (kNN) model

The dataset used is: **Mavoglurant_A2121_nmpk.csv**

It contains repeated measurements of drug concentration over time for different individuals after receiving different doses of the drug.

## Data Processing

The following preprocessing steps were performed:

- Observations with **OCC = 2** were removed to keep only one dosing occasion per individual.
- Rows with **TIME = 0** (dosing records) were excluded when calculating drug exposure.
- Total drug exposure (**Y**) was calculated as the **sum of DV values for each individual**.
- Subject-level variables were extracted from the TIME = 0 rows.
- **SEX** and **RACE** were converted to factor variables.

The final dataset contains **120 observations**.

## Models

The following models were fitted:

**Linear regression**
- Y ~ DOSE
- Y ~ DOSE + AGE + SEX + RACE + WT + HT

Model performance evaluated using:
- RMSE
- R²

**Logistic regression**
- SEX ~ DOSE
- SEX ~ DOSE + AGE + RACE + WT + HT + Y

Model performance evaluated using:
- Accuracy
- ROC-AUC

**k-nearest neighbors (kNN)**
- Y predicted using DOSE, AGE, WT, and HT
