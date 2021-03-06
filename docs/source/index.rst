explainerdashboard
******************

Summary
=======

``explainerdashboard`` is a library for quickly analyzing and explaining the performance
of a (scikit-learn compatible) machine learning models.

It combines shap values, permutation importances, partial dependence plots,
and the visualisation of individual trees of random forests into a single package.

You can easily construct an ``Explainer`` object that computes all relevant
statistics behind the scenes and allows you to quickly plot feature importances,
shap dependence plots, pdp plots, etc.

You then pass this ``Explainer`` object to an ``ExplainerDashboard`` to start an interactive
analytical web app to inspect the workings and performance of your model.

Or you can use the primitives provided by the ``Explainer`` to construct your own
project-specific dashboard using plotly dash. 

Example
=======

Some example code::

    from sklearn.ensemble import RandomForestClassifier

    from explainerdashboard.explainers import RandomForestClassifierExplainer
    from explainerdashboard.dashboards import ExplainerDashboard
    from explainerdashboard.datasets import titanic_survive, titanic_names

    X_train, y_train, X_test, y_test = titanic_survive()
    train_names, test_names = titanic_names()

    model = RandomForestClassifier(n_estimators=50, max_depth=5)
    model.fit(X_train, y_train)

    explainer = RandomForestClassifierExplainer(
                    model, X_test, y_test, 
                    cats=['Sex', 'Deck', 'Embarked'],
                    idxs=test_names,
                    labels=['Not survived', 'Survived'])

    ExplainerDashboard(explainer).run()

The result of the lines above can be viewed on `this dashboard deployed to heroku. <http://titanicexplainer.herokuapp.com>`_

More examples can be found in the `example notebook on the github repo. <https://github.com/oegedijk/explainerdashboard/blob/master/dashboard_examples.ipynb>`_


.. toctree::
   :maxdepth: 3

   explainers
   plots
   dashboards
   explainer_methods
   explainer_plots
   license
   help


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
