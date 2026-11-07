# Student Performance Analysis and Prediction

## Project Overview

A machine learning project that analyzes and predicts student academic performance using Python. This project compares early and late prediction models for Mathematics and Portuguese using the UCI Student Performance dataset.

## Objectives

- Analyze student academic performance and study habits.
- Explore relationships between student characteristics and final grades.
- Build early and late prediction models.
- Compare model performance using MAE and R².
- Identify influential features using permutation importance.
- Evaluate model reliability through five-fold cross-validation.

## Dataset

**Source:** [UCI Student Performance Dataset](https://archive.ics.uci.edu/dataset/320/student+performance)

- Mathematics records: 395
- Portuguese records: 649
- Combined records: 1,044
- Target variable: `G3` (final grade, on a 0–20 scale).

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Google Colab

## Methodology

1. Data collection and preparation.
2. Exploratory data analysis.
3. Subject-wise performance comparison.
4. Linear regression modelling.
5. Early versus late prediction.
6. Five-fold cross-validation.
7. Residual analysis.
8. Permutation feature importance.

## Prediction Models

### Early Prediction

Uses eight features without previous examination grades:

- Study time
- Absences
- Age
- Previous failures
- School support
- Family support
- Internet access
- Higher education intention

Categorical features are processed using OneHotEncoder.

### Late Prediction

Uses:

- Study time
- Absences
- First-period grade (`G1`)
- Second-period grade (`G2`)

## Model Evaluation Results

Results obtained using five-fold cross-validation and out-of-fold predictions.

| Subject | Stage | MAE | R² |
|---|---|---:|---:|
| Mathematics | Early | 3.3221 | 0.0927 |
| Mathematics | Late | 1.1852 | 0.8217 |
| Portuguese | Early | 2.0802 | 0.2300 |
| Portuguese | Late | 0.7935 | 0.8442 |

### Feature Importance

Five-fold permutation importance identified the following leading features:

**Mathematics**
- Previous failures: 0.3133
- School support: 0.0825
- Age: 0.0752

**Portuguese**
- Previous failures: 0.2267
- Higher education intention: 0.1375
- Study time: 0.0756

Previous academic failures were the strongest early-prediction feature in both subjects.

## Key Findings

- Late prediction models performed substantially better than early prediction models.
- Previous examination grades provided strong predictive information about final grades.
- Previous academic failures were consistently important in early prediction.
- Predictive performance differed between Mathematics and Portuguese.
- Student characteristics alone provided limited predictive power, particularly for Mathematics.

## Limitations

- The dataset contains records from two Portuguese schools and is relatively small.
- The analysis identifies associations, not causal relationships.
- The models have not been externally validated on students from new schools.
- Late prediction requires previous examination grades to be available.
- Feature importance can vary across validation folds.

## Conclusion

This project demonstrates how machine learning and data analysis can be used to investigate student academic performance. Comparing early and late prediction scenarios highlights the predictive value of previous examination grades and the challenges of forecasting academic outcomes using student characteristics alone.

## Future Improvements

- Experiment with Random Forest and other regression algorithms.
- Explore additional feature engineering techniques.
- Evaluate models on independent datasets.
- Investigate explainable machine learning methods.

## Author

CSE Undergraduate Student

## Project Notebook

See `Student_Performance_Analysis.ipynb` in this repository for the complete analysis and implementation.
