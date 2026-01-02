# Understanding Student Performance
Factors Influencing Academic Success and Performance Consistency

## Project Overview
This project analyzes the academic performance of Portuguese high-school students to identify key socio-economic, demographic, and educational factors that influence student outcomes.

The analysis focuses on two main aspects:
1. Final exam performance
2. Consistency of improvement or decline across multiple exams

The project emphasizes statistical interpretability over black-box prediction accuracy, making the results useful for educators, policymakers, and academic researchers.

## Objectives
- Identify factors influencing final academic performance
- Analyze trends in student performance over time
- Understand the impact of family background, study habits, and school support
- Provide interpretable statistical insights rather than opaque predictions

## Dataset
- Source: UCI Machine Learning Repository – Student Performance Dataset
- Students: 650 Portuguese secondary-school students
- Features: Approximately 30 demographic, academic, and lifestyle variables
- Grades:
  - G1: First period
  - G2: Second period
  - G3: Final exam (out of 20)

The dataset is stored in:


## Data Processing and Feature Engineering
The following preprocessing steps were applied:

- Outlier handling: Extreme values in the absences variable were detected using the interquartile range (IQR) method and replaced with the mean.
- Grade normalization: Raw grades (G1, G2, G3) were converted into percentiles (G1_perc, G2_perc, G3_perc) to enable comparison across exams.
- Performance consistency flag: A binary variable was created to track trends:
  - Flag = 1 if G3 > G2 > G1 (consistent improvement)
  - Flag = 0 if G1 > G2 > G3 (consistent decline)

## Exploratory Data Analysis
Exploratory analysis was conducted to understand distributions, trends, and relationships:

- Scatter plots with LOWESS smoothing for numeric variables
- Box plots for binary and nominal variables
- Outlier and distribution analysis
- Visual assessment of how student characteristics relate to performance

All analysis was performed using R and RMarkdown.

## Modeling Approach

### Linear Regression
- Target variable: Final exam percentile (G3_perc)
- Purpose: Identify interpretable predictors of academic success
- Key observations:
  - Study time and parental education positively affect performance
  - Prior academic failures strongly reduce final grades
  - School support shows a negative association, likely reflecting targeted intervention
- Model performance: R² approximately 0.33–0.38

### Logistic Regression
- Target variable: Performance consistency flag
- Purpose: Understand factors associated with improvement versus decline
- Evaluation:
  - 70/30 train-test split
  - Confusion matrix and accuracy assessment
- Accuracy: Approximately 0.59
- The model is not intended for high-precision prediction but for factor interpretation

## Key Findings
- Student performance is influenced by a complex interaction of academic, family, and institutional factors
- Interpretable statistical models provide meaningful insights even with moderate predictive power
- Performance consistency is not strongly influenced by extracurricular activities, internet access, or alcohol consumption
- Results highlight areas for further educational research and policy consideration

## Project Structure
student-performance-analysis/
├── README.md
├── data/
│   └── student-por.csv
├── notebooks/
│   ├── final.Rmd
│   └── Untitled.Rmd
├── reports/
│   ├── Final_Project.pdf
│   ├── 893_presentation.pdf
│   ├── final.tex
│   ├── final.log
│   ├── final_1.tex
│   └── final_1.log




## How to Reproduce
1. Clone the repository
2. Open notebooks/final.Rmd in RStudio
3. Install required R packages (ggplot2, caret, etc.)
4. Knit the RMarkdown file to reproduce the analysis and results

## Notes
- This project prioritizes interpretability and statistical reasoning
- Findings should be interpreted as associative, not causal
- Suitable for academic coursework, applied statistics portfolios, and data analysis roles

## Authors
- Parimal
