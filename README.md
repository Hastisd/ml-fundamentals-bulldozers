# ml-fundamentals-bulldozers


# Bluebook for Bulldozers: Price Prediction with Random Forest

This is a practice project from the Zero to Mastery machine learning course. The dataset and the overall structure come from the course. I worked through it to learn the scikit-learn workflow from start to finish on a real tabular dataset.

## Goal

Predict the sale price of used bulldozers from their features, such as year made, machine hours, product size and state of sale.

## What I learned

- **Data preparation:** I parsed dates, created new features from the sale date (year, month, day, day of week, day of year), and converted text columns into categories.
- **Missing values:** I filled missing numeric values with the median and added a column for each one that shows which rows were missing. I encoded categorical features with `OrdinalEncoder`.
- **Time-ordered split:** I split the data into training and validation sets by date. Random splitting would let the model see the future, so the date split gives a more honest result.
- **Modelling and tuning:** I trained a `RandomForestRegressor`, tuned it with `RandomizedSearchCV`, and compared models using MAE, RMSLE and R². I saved the best model with `joblib`.
- **Interpretation:** I looked at feature importance to see which features the model used most, and I tested the model on a custom example from an online auction listing.

## Results

Best validation RMSLE

## Data

The dataset is not included in this repository because of its size. The notebook downloads it in the first cell. It is also available from the [course data folder](https://github.com/mrdbourke/zero-to-mastery-ml/tree/master/data).

## How to run

1. Open `bulldozer-v2.ipynb` in Google Colab or Jupyter.
2. Run all cells from top to bottom.

## Limitations

- The data comes from a course exercise, and I did not collect it myself.
- Hyperparameter search was short, so better settings may exist.
- Categorical features are encoded as ordinal numbers, which is simple but not the only option.

## Tools

Python, pandas, NumPy, matplotlib, scikit-learn
