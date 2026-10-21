# House price prediction (Boston dataset)

Comparison of 5 regression methods to predict median house prices.

## Data
Boston housing dataset (506 houses, 13 features). Column B is removed
because it is based on the racial make-up of each town.

## Methods
Linear regression, polynomial features (degree 2), Ridge, Lasso, PCA + linear.
60/20/20 train/validation/test split; alpha chosen on validation.

## Results

Validation set (sorted by R²):

| model | val R2 | val RMSE |
|---|---|---|
| Ridge (poly) | 0.759 | 4.387 |
| Lasso (poly) | 0.758 | 4.397 |
| Polynomial | 0.754 | 4.429 |
| Linear | 0.639 | 5.370 |
| PCA + linear | 0.604 | 5.620 |

Best model on the test set: **Ridge (poly)**, R2 = 0.885, RMSE = 3.13.

## Conclusion

Adding polynomial features improved the validation R2 from 0.64 (linear) to about 0.75, so the relationship between the features and the price is not linear. Ridge, Lasso and plain polynomial regression are very close (0.759, 0.758, 0.754), so the differences between them are too small to say that one is really better. I picked Ridge because it had the best validation score. PCA + linear was the weakest model, which means the compression lost useful information.

On the test set, Ridge reached R2 = 0.885 (RMSE = 3.13), which is higher than on validation. I think this is mostly luck from the split: the test set has only about 100 houses, so the score changes a lot depending on which houses it contains. The scatter plot shows that the model underestimates the most expensive houses (real price around 50, predicted around 41), probably because prices in this dataset are capped at 50.

Next steps: use cross-validation instead of one split to get a more reliable comparison, and try a tree-based model such as random forest.


pip install numpy pandas scikit-learn matplotlib
Put the CSV next to the notebook and run boston_house_prices.ipynb.
