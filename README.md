# Health Insurance Cross-Sell Prediction

This project analyzes a binary classification problem based on the **Health Insurance Cross Sell Prediction** dataset. The objective is to predict whether existing health insurance customers would be interested in purchasing vehicle insurance.

The project was developed as a final assignment for a Data Science course.

## Objective

The main goal is to identify customers with a higher probability of accepting a vehicle insurance offer. Since the dataset is imbalanced, the evaluation does not rely only on accuracy. Instead, the analysis focuses on metrics that are more informative for the positive class.

## Dataset

The dataset contains demographic, vehicle-related and commercial information about insurance customers, including:

- Age
- Gender
- Driving license
- Region code
- Previous insurance status
- Vehicle age
- Vehicle damage
- Annual premium
- Policy sales channel
- Vintage
- Response

The target variable is `Response`, where:

- `1` indicates that the customer accepted the offer.
- `0` indicates that the customer did not accept the offer.

The original dataset is publicly available on Kaggle under the name **Health Insurance Cross Sell Prediction**.

The file `train.csv` is included in the `data/` folder to make the notebook easier to reproduce.

## Methodology

The project includes:

- Exploratory data analysis
- Data preprocessing
- Encoding of categorical variables
- Feature scaling
- Train-test split
- Analysis of class imbalance
- Model training and comparison
- Evaluation using classification metrics

## Models evaluated

The following models were compared:

- Naive Bayes
- Linear Discriminant Analysis
- Logistic Regression
- SGDClassifier
- Gradient Boosting
- Random Forest
- XGBoost
- HistGradientBoosting

## Evaluation metrics

Because the dataset is imbalanced, the models were evaluated using:

- Precision
- Recall
- F1-score
- ROC-AUC
- Average Precision
- Confusion matrix

## Main conclusion

The selected model was **XGBoost**, trained on the original dataset with imbalance-aware configuration. This model achieved a good trade-off between recall, ROC-AUC and Average Precision.

From a business perspective, recall is particularly relevant because the objective is to identify as many potentially interested customers as possible. A false negative may imply losing a commercial opportunity, while a false positive mainly represents an additional marketing or contact cost.

## Repository structure

```text
insurance-cross-sell-prediction/
│
├── README.md
├── health_insurance_cross_sell_prediction.ipynb
├── .gitignore
└── data/
    ├── README.md
    └── train.csv
```

## Reproducibility

Some training cells may take several minutes to run, especially ensemble models such as Random Forest, Gradient Boosting and XGBoost.

To reproduce the notebook, run the following path configuration:

```text
file_path = "data/train.csv"
```
