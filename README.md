# House price prediction (Boston dataset)

Comparison of 5 regression methods to predict median house prices.

## Data
Boston housing dataset (506 houses, 13 features). Column B is removed
because it is based on the racial make-up of each town.

## Methods
Linear regression, polynomial features (degree 2), Ridge, Lasso, PCA + linear.
60/20/20 train/validation/test split; alpha chosen on validation.

## Results
| model | val R2 | val RMSE |
|---|---|---|
| ... | ... | ... |

Best model on test set: [model], R2 = [x], RMSE = [y].

## Run it
pip install numpy pandas scikit-learn matplotlib
Put the CSV next to the notebook and run boston_house_prices.ipynb.
