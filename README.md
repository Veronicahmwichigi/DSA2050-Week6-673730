# DSA 2050 Week 6: Regression and Baseline Comparison

## Student Details
- **Student Name:** Mwichigi Veronicah
- **Student ID:** 673730
- **Course:** DSA 2050 – Data Science Methodology

## Lab Objective
The objective of this lab was to build and compare regression models for predicting sales in Kenyan shillings (KES). The lab focused on comparing models with simple baselines, preparing data safely, evaluating prediction errors, using cross-validation, and checking residuals, subgroup errors, and overfitting.

## Dataset
The dataset, `DSA2050_Week6_Sales_Data.csv`, contains business information used to predict `Sales_KES`.

Features used:
- `AdvertisingSpend_KES`
- `StoreVisits`
- `DiscountPercent`
- `Region`
- `CustomerSegment`
- `ProductCategory`

The target variable was **`Sales_KES`**.

## Models Compared
The following models were evaluated:
1. Mean Baseline
2. Median Baseline
3. Linear Regression
4. Ridge Regression
5. Decision Tree Regressor (shallow tree)

The data was split into 80% training data and 20% testing data. Numeric and categorical features were prepared using a preprocessing pipeline. Five-fold cross-validation was performed on the training data.

## Best Model and Results
Based on the saved test results, **Ridge Regression** performed best overall among the candidate models.

| Model | Test MAE (KES) | Test R² |
|---|---:|---:|
| Mean Baseline | 39,197.16 | -0.008 |
| Median Baseline | 39,146.75 | -0.006 |
| Linear Regression | 13,757.84 | 0.870 |
| Ridge Regression | 13,714.40 | 0.870 |
| Decision Tree | 23,775.92 | 0.648 |

**Selected model MAE:** KES 13,714.40.

MAE (Mean Absolute Error) represents the average absolute difference between the predicted sales and the actual sales. In this case, Ridge Regression's predictions were off by about KES 13,714 on average on the test set.

*Note: These are the results saved in the notebook. Re-run all notebook cells before submission and update this table if the results change.*

## Key Findings
1. **Ridge Regression performed much better than the baselines.** Its test MAE was about KES 13,714, compared with about KES 39,147 for the median baseline. This suggests the model used the available business features to make more useful predictions than simply predicting a typical sales value.
2. **A deep Decision Tree showed signs of overfitting.** Its training MAE was KES 0.00, while its test MAE was KES 26,797.50. This means it fitted the training data extremely closely but performed less accurately on unseen data.

## Limitations
1. **Limited predictors:** The dataset may not include all factors that affect sales, such as seasonality, competitor prices, product availability, or special promotions.
2. **Limited or teaching dataset:** The dataset may not represent every real-world sales situation, so the results may not generalize to all businesses.
3. **Prediction does not prove causation:** A relationship between a feature and sales does not prove that the feature causes sales to increase or decrease.

## Files
- `DSA2050_Week6_Guided_Regression_Lab.ipynb` — notebook containing the code, model comparisons, and analysis.
- `DSA2050_Week6_Sales_Data.csv` — dataset used in the lab.
- `README.md` — project overview, results, findings, and limitations.

## How to Run
1. Download or clone this repository.
2. Make sure the notebook and CSV file are in the same folder.
3. Install the required Python libraries if needed:
   ```bash
   pip install pandas numpy matplotlib scikit-learn jupyter
   ```
4. Open the notebook in Jupyter Notebook or VS Code.
5. Restart the kernel and run all cells from top to bottom.

