# Car Price Prediction — Intermediate Assessment

Submission for the automobile pricing regression assignment. The notebook loads the supplied 205-car CSV, checks and preprocesses it, trains five requested regressors, compares held-out R²/MSE/MAE, ranks predictors using permutation importance, and tunes Random Forest and Gradient Boosting with training-only cross-validation.

## Run

```bash
python -m pip install -r requirements.txt
jupyter notebook Car_Price_Prediction.ipynb
```

Open the notebook and select **Run All**. Run from this folder; the CSV lives in `data/`. Python 3.10+ is recommended. Results are reproducible with random seed 42. The dataset is for educational analysis and does not represent verified current US pricing.

## GitHub submission

Create a new GitHub repository, upload this folder's `Car_Price_Prediction.ipynb`, `README.md`, `requirements.txt`, and `data/CarPrice_Assignment.csv`, then submit the URL of the notebook in your repository. You can also run `git init`, commit the four files, and push to your own repository. No GitHub account access is needed to run the project locally.

## Observed results (random seed 42)

| Baseline model | Test R² | Test MAE |
| --- | ---: | ---: |
| Random Forest | 0.958 | 1,270.78 |
| Gradient Boosting | 0.928 | 1,666.64 |
| Decision Tree | 0.906 | 1,785.78 |
| Linear Regression | 0.901 | 1,807.70 |
| Support Vector Regressor | 0.505 | 3,489.50 |

The strongest measured predictors were engine size and curb weight. Cross-validation selected tuned Gradient Boosting, but its held-out R² (0.923) was below its untuned R² (0.928). Full MSE values and tuning parameters appear in the notebook.
