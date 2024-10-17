# Gene-Environment Interaction in Depression: A Multiple Regression Analysis

This repository contains the code and analysis for the **Multiple Regression Computing Project** from the course AMS 578: Regression Analysis, Spring 2020. The project focuses on analyzing a dataset to find the best regression model for predicting a dependent variable using a combination of environmental and genetic factors, as outlined in the paper by [Caspi et al](https://pubmed.ncbi.nlm.nih.gov/19531786/).

## Project Overview

The goal of this project is to estimate the function that was used to generate the data based on gene-environment interactions. The data includes:
- 6 environmental variables (E1 to E6)
- 20 genetic indicator variables (G1 to G20)
- A dependent variable \( Y \) representing some outcome related to depression

This project explores:
- Handling missing data using **Multivariate Imputation by Chained Equations (MICE)**.
- Correlation analysis to select significant variables.
- Box-Cox transformation to handle non-normality in the dependent variable.
- Stepwise regression to build the final model.
- Residual analysis and validation to ensure model adequacy.

## Methods

The key steps involved in the analysis are:
1. **Data Preprocessing**: 
   - Imputation of missing values using MICE.
   - Summary statistics for all variables.
2. **Variable Selection**: 
   - Pearson correlation tests to select significant variables with low p-values.
3. **Model Transformation**: 
   - Box-Cox transformation to correct for non-constant variance in the dependent variable.
4. **Model Building**: 
   - Stepwise regression using the BIC criterion to estimate the best model.
5. **Residual Analysis**: 
   - Shapiro-Wilk test to verify normality of residuals.

## Results

The final model selected includes the following significant terms:

\[
Y = 15.967 + 0.131E1 + 0.243G1 + 0.293G16 + 0.132G1:G16
\]

Where:
- **\( E1 \)**: Environmental variable 1
- **\( G1 \)**: Genetic indicator 1
- **\( G16 \)**: Genetic indicator 16
- **\( G1:G16 \)**: Interaction term between \( G1 \) and \( G16 \)

The model explained approximately 59% of the variance in \( Y \) (Adjusted \( R^2 = 0.5874 \)).