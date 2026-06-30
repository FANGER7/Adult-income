# Adult Income Prediction

A Machine Learning project that predicts whether an individual's annual income exceeds **$50,000** based on demographic and employment-related attributes from the UCI Adult Income Dataset.

---

## Project Overview

The objective of this project is to build a robust classification model capable of predicting income categories:

- **<=50K**
- **>50K**

This project includes:

- Data Cleaning and Preprocessing
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Baseline Model Comparison
- Hyperparameter Tuning
- Model Persistence using Joblib
- Production-Ready Inference System

---

## Dataset

**Dataset:** UCI Adult Income Dataset

The dataset contains demographic and employment information collected from the 1994 US Census.

### Features Include:

- Age
- Workclass
- Education
- Occupation
- Marital Status
- Relationship
- Race
- Gender
- Capital Gain
- Capital Loss
- Hours per Week
- Native Country

### Target Variable

```text
income
0 → <=50K
1 → >50K
```

---

## Repository Structure

```text
Adult-income/
│
├── Adult_income_final.ipynb
├── ML_Assignment_03_Adult_Income.pdf
├── adult.csv
├── inference.py
├── artifacts/
│   └── income_pipeline.pkl
└── README.md
```

---

## Project Workflow

### 1. Data Cleaning

- Detected hidden missing values represented by `'?'`
- Replaced missing values with `NaN`
- Removed leading/trailing whitespaces
- Encoded target labels

### 2. Feature Engineering

The following features were engineered:

- `age_group`
- `hours_category`
- `capital_net`
- `is_married`
- `education_level`

These features were created to improve model performance and capture additional insights from the dataset.

### 3. Data Preprocessing

The preprocessing pipeline includes:

- Missing value imputation
- Feature scaling for numerical variables
- One-hot encoding for categorical variables
- ColumnTransformer integration

---

## Machine Learning Models Evaluated

The following models were trained and compared:

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier

Evaluation metrics used:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC Score

Cross-validation was performed using **Stratified K-Fold Cross Validation**.

---

## Hyperparameter Tuning

The best-performing baseline model was optimized using:

```python
RandomizedSearchCV(
    n_iter=30,
    cv=StratifiedKFold(),
    scoring='roc_auc'
)
```

This helped improve the model's overall performance and generalization capability.

---

## Model Persistence

The final trained pipeline was saved using:

```python
joblib.dump()
```

Saved Model:

```text
artifacts/income_pipeline.pkl
```

The saved pipeline contains:

- Preprocessing steps
- Feature transformers
- Encoders
- Trained classifier

This allows predictions to be made without retraining the model.

---

## Inference Module

The project includes a standalone **inference.py** script for production-ready predictions.

### Features

- Loads the trained pipeline
- Validates input schema
- Performs feature engineering
- Generates predictions
- Returns structured output

### Example Output

```python
{
    "prediction": 1,
    "label": ">50K",
    "probability": 0.9234
}
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Joblib

---

## Installation

Clone the repository:

```bash
git clone https://github.com/FANGER7/Adult-income.git
```

Move into the project directory:

```bash
cd Adult-income
```

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

---

## Running the Project

### Open the Notebook

```bash
jupyter notebook Adult_income_final.ipynb
```

### Run the Inference Script

```bash
python inference.py
```

---

## Future Improvements

- Deploy using Django REST Framework
- Build a Web Interface
- Containerize using Docker
- Add CI/CD pipeline
- Deploy as a REST API

---

## Author

**Kanishk Chahar**

B.Tech Computer Science Engineering  
Machine Learning Enthusiast

GitHub: https://github.com/FANGER7

---

## References

- https://www.kaggle.com/datasets/uciml/adult-census-income
- https://scikit-learn.org/stable/
- https://joblib.readthedocs.io/

---

⭐ If you found this project useful, consider giving this repository a star.
