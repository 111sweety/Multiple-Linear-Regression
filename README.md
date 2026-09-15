# Multiple Linear Regression

This project uses multiple linear regression to predict product sales from advertising budgets for TV, radio, and newspaper campaigns. The complete analysis is contained in [multiple-linear-regression.ipynb](multiple-linear-regression.ipynb).

## Dataset

The project uses `Advertising.csv`, a dataset with 200 observations. The values are reported in thousands:

| Column | Description |
| --- | --- |
| `TV` | TV advertising budget |
| `radio` | Radio advertising budget |
| `newspaper` | Newspaper advertising budget |
| `sales` | Product sales |

The original CSV includes an unnamed index column. The notebook removes it before analysis.

## Workflow

The notebook follows these steps:

1. Load the dataset with pandas.
2. Inspect the shape, columns, data types, summary statistics, and missing values.
3. Visualize feature relationships with regression plots and a pair plot.
4. Check correlations and discuss multicollinearity.
5. Split the data into training and test sets using an 80/20 split with `random_state=42`.
6. Standardize the three input features using `StandardScaler`, fitting the scaler on the training data only.
7. Train a scikit-learn `LinearRegression` model.
8. Evaluate training and test predictions with MAE, MSE, RMSE, $R^2$, and adjusted $R^2$.

## Requirements

- Python 3
- Jupyter Notebook or VS Code with the Jupyter extension

Install the Python dependencies with:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

## Run the project

1. Clone or download this repository.
2. Keep `Advertising.csv` in the same directory as the notebook.
3. Open `multiple-linear-regression.ipynb` in Jupyter or VS Code.
4. Run the cells from top to bottom.

## Results

Using the recorded notebook run and the 80/20 split:

| Metric | Training set | Test set |
| --- | ---: | ---: |
| MAE | 1.1985 | 1.4608 |
| MSE | 2.7051 | 3.1741 |
| RMSE | 1.6447 | 1.7816 |
| $R^2$ | 0.8957 | 0.8994 |
| Adjusted $R^2$ | 0.8937 | 0.8911 |

The test $R^2$ indicates that the model explains approximately 89.94% of the variation in sales for this split. TV has the strongest observed relationship with sales, followed by radio; newspaper has a comparatively weak relationship.

## Fitted model

The notebook fits the following model after standardizing the input features:

```text
Sales = 14.10 + 3.7642 * TV_scaled + 2.7923 * radio_scaled + 0.0560 * newspaper_scaled
```

Because the predictors are standardized, these coefficients describe the change in predicted sales for a one-standard-deviation increase in each advertising channel, while holding the other standardized features constant. They should not be interpreted as raw-budget coefficients without converting the model back to the original feature scale.

## Notes

- Correlations between the independent variables are below the notebook's `0.7` threshold, so no feature was removed for multicollinearity.
- The notebook scales only the independent variables; the target `sales` remains in its original units.
- The reported metrics depend on the chosen train/test split and random seed.