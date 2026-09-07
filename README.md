# university-dropout-prediction-using-ml
A machine learning-based system for predicting university student dropout and identifying key factors associated with academic success and dropout risk.
# Student Dropout Prediction

## Project Overview

This project develops a machine learning system to predict student dropout risk using student academic, demographic, financial, and enrollment-related information.

The target variable is binary:

* `Dropout = 1`
* `Graduate = 0`

Students with the `Enrolled` outcome are excluded from the binary classification task.

## Dataset

The project uses `data.csv` as the input dataset.

The dataset is loaded using the semicolon (`;`) separator.

## Methodology

The project follows these main steps:

1. Load and validate the dataset.
2. Check duplicate values and missing values.
3. Remove variables that are not suitable for modelling.
4. Engineer `Discipline_Group` from the original `Course` variable.
5. Split the dataset using a stratified:

   * 70% Training set
   * 15% Validation set
   * 15% Test set
6. Apply preprocessing:

   * Median imputation and standard scaling for numerical variables.
   * Most-frequent imputation and one-hot encoding for categorical variables.
7. Train and compare several machine learning models.
8. Tune selected models using 5-fold Stratified Cross-Validation.
9. Select the best model based on validation F1-score.
10. Evaluate the selected model once on the untouched test set.
11. Save the final model and evaluation artifacts.

## Machine Learning Models

The project compares:

* Majority-class Dummy Classifier baseline
* Logistic Regression
* K-Nearest Neighbors (KNN)
* Random Forest
* Gradient Boosting

Both untuned and tuned versions are considered where applicable.

## Reproducibility

The project uses a fixed random seed:

```text
RANDOM_SEED = 42
```

This is used for data splitting and applicable model/training procedures.

The preprocessing steps and classifier are stored together in the final scikit-learn pipeline.

## How to Run in Google Colab

### Step 1: Open the notebook

Open the following notebook in Google Colab:

`DropoutPredictor_Updated_70_15_15_Sadiya_FINAL.ipynb`

### Step 2: Upload the dataset

Upload:

`data.csv`

The dataset should be available in the same working directory as the notebook.

### Step 3: Run the notebook

In Google Colab, select:

**Runtime → Run all**

Run all cells from beginning to end.

### Step 4: Check generated files

After successful execution, the following files will be generated:

* `final_model.joblib`
* `data_dictionary.csv`
* `model_comparison_results.csv`
* `final_test_results.csv`
* `validation_model_comparison_results.csv`

Download these files from the Colab Files panel.

## Output Files

### `final_model.joblib`

Contains the selected final machine learning pipeline, including preprocessing and the final classifier.

### `data_dictionary.csv`

Contains the data dictionary describing the original, engineered, retained, and removed variables used in the project.

### `model_comparison_results.csv`

Contains the validation-set performance comparison of the candidate models.

### `final_test_results.csv`

Contains the final evaluation metrics of the selected model on the untouched test set.

### `validation_model_comparison_results.csv`

Compatibility copy of the validation model comparison results.

## Project Files

```text
Student_Dropout_Project/
│
├── data.csv
├── DropoutPredictor_Updated_70_15_15_Sadiya_FINAL.ipynb
├── final_dropout_prediction_code.py
├── final_model.joblib
├── data_dictionary.csv
├── model_comparison_results.csv
├── final_test_results.csv
├── validation_model_comparison_results.csv
├── requirements.txt
├── README.md
└── Student_Dropout_Prediction_Final_Report.docx
```

## Important Note

The test set is kept separate from model selection and tuning. Candidate models are compared using the validation set, and the test set is reserved for the final evaluation of the selected model.

## Author

Sadiya Mohon Auti
Tasmia amin

## Project Type

Python Final Term Machine Learning Project
