
# TODO:
- fix hit enter on input field reloads page on decision tree tab
- let plots autodetect if col in cats
- Interaction feature stuck on one feature? (e.g. No_of_relatives onboard on heroku?)
- find out why dtreeviz for regression no longer working
- find a way to plot individual xgboost trees

## Layout:
- Find a proper frontender to help :)

## dfs:
- wrap shap values in pd.DataFrames?
- wrap predictions in pd.Series?

## Plots:
- Add options sorting contributions plot from most negative to most positive
- fix name of figure MEAN_ABS_SHAP
- Add Altair (vega) plots for easy inclusion in websites
- rename plotly_ from all plotting functions? or not if we're going to add altair?

### Classifier plots:
- Classification plot: add percentage in totals plot, add totals in percentage plot
- plot_precision: default no cutoff
- plot_precision: round percentages
- Add feature names to waterfall plot
- fix percentages difference bug lift plot vs classification plot

### Regression plots:
- regression plots: only take log of x-axis or y-axis
- add cats option (violin plots?) to plot_residuals_vs_feature
- add log ratio

## Explainers:
- add get_random_index with min/max residual for regression

## Dashboard:
- add option for vertical contributions?
- reformat contributions table
- add final prediction to contributions table

## Methods:
- Multiprocessing shap summary graph 
- Move pdp function to explainer_methods.py
- Add LIME, Shaabas values for completeness?
- refactor for loop in contrib_df_summary

## Tests:
- add multiclass classifier tests
- add individual dashboard tests
- add ExplainerDashboard intergration test
- Add tests for decisiontrees, extratrees
- test model_output='probability' and 'raw' or 'logodds' seperately

# Docs:
- document X_background
- document properties with prop(pos_label)
- document model_output
- add deploying with flask/gunicorn section

## Library level:
- submit pull request to dtreeviz to accept shadowtree as parameter
- turn all docstrings into sphinx-napolean google style

