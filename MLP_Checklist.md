# Machine Learning Project Checklist
(Source: [Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow, 2nd Edition](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/))

## Frame the Problem

- [] Define objectives in practical/business terms.
- [] How will your solution be used?
- [] What are the existing solutions (if any)?
- [] How should you frame your project (supervise/unsupervised, online/offline, etc.)
- [] How should performance be measured?
- [] Is the performance measure aligned with the practical/business objectives?
- [] What would be the minimum performance needed to reach the practical/business objective?
- [] What are comparable problems? Can you reuse experience or tools?
- [] Is human expertise available?
- [] How would you solve the problem manually?
- [] List the assumptions you (or others) have made so far.
- [] Verify the assumptions if possible.

## Get the Data

Note: automate this part as much as possible so that you can easily get fresh data.

- [] List de data you need and how much you need.
- [] Find and document where you can get the data.
- [] Check how much space it will take.
- [] Check legal obligations and get authorization if necessary.
- [] Get access authorizations.
- [] Create a workspace (with enough storage space).
- [] Get the data.
- [] Convert the data toa format you can easily manipulate (without changing the data itself).
- [] Ensure sensitive information is deleted or protected (e.g., anonymized).
- [] Check the size and type of data (time series, sample, geographical, etc.).
- [] Sample a test set, put it aside, and never look at it (no data snooping!)

## Explore the Data

Note: try to get insight from the field expert for these steps.

- [] Create a copy of the data for exploration (sampling it down to a manageable size if necessary).
- [] Create a Jupyter notebook to keep a record of your data exploration.
- [] Study each attribute and its characteristics:
	- Name
	- Type (categorical, int/float, bounded/unbounded, text, structured, etc.)
	- % missing values
	- Noisiness and type of noise (stochastic, outliers, rounding errors, etc.)
	- Usefulness for the task
	- Type of distribution (Gaussian, uniform, logarithmic, etc.)
- [] For supervised learning tasks, identify the target attribute(s).
- [] Visualize data
- [] Study the correlations between attributes.
- [] Study how you would solve the problem manually.
- [] Identify the promising transformations you may want to apply.
- [] Identify extra data that would be useful (go back to "Get the Data")

## Prepare the Data
- Notes:
	- Work on copies of the data (keep the original data intact)
	- Write functions for all data transformations you apply, for five reasons:
		- So you can easily prepare the data the next time you get a fresh dataset
		- So you can apply these transformations in future projects
		- To clean and prep the test set
		- To clean and prepare new data instances once your solution is live
		- To make it easy to use your preparation choices as hyperparameters
- Data cleaning:
	- [] Fix or remove outliers (optional).
	- [] Fill in missing values (e.g., with zero, mean, median, etc.) or drop their rows (or columns).
- [] Feature selection (optional): Drop the attributes that provide no useful information for the task.
- Feature engineering:
	- [] Discretize continuous features (where appropriate).
	- [] Decompose features (e.g., categorical, data/time, etc.) (where appropriate).
	- [] Add promising transformations of features (e.g., log(x), sqrt(x), x^2, etc.) (where appropriate).
	- [] Aggregate features into promising new features (where appropriate).
- [] Feature scaling: Standardize or normalize features.

## Shortlist Promising Models

- Notes:

	- If the data is huge, you may want to sample smaller training sets so you can train many different models in a reasonable time (be aware that this penalizes complex models such as large neural nets or Random Forests).
	- Try to automate these steps as much as possible.

- [] Train many quick-and-dirty models from different categories (e.g., linear, naive Bayes, SVM, Random Forest, neural net, etc.) using standard parameters.
- [] Measure and compare their performance. For each model, use N-fold cross-validation and compute the mean and standard deviation of the performance measure on the N folds.
- [] Analyze the most significant variables for each algorithm.
- [] Analyze the types of errors the models make. What data would a human have used to avoid these errors?
- [] Perform a quick round of feature selection and engineering.
- [] Perform one or two more rounds of the five previous steps.
- [] Shortlist the top three to five most promising models, preferring models that make different types of errors.

## Fine-Tune the System

- Notes:
	- You will want to use as much data as possible for this step, especially as you move toward the end of the fine-tuning.
	- As always, automate what you can.

- Fine-tune the hyperparameters using cross-validation:
	- [] Treat your data transformation choices as hyperparameters, especially when you are not sure about them (e.g., if you are not sure whether to replace missing values with zero or with the median value, or to just drop the rows).
	- [] Unless there are very few hyperparameter values to explore, prefer random search over grid search. If tuning is very long you may prefer a Bayesian optimization approach (e.g. using Gaussian process priors, as described by [Jasper Snoek et al.](http://homl.info/134))
- [] Try Ensemble methods. Combining your best models will often produce better performance than running them individually.
- [] Once you are confident about your final model, measure its performance on the test set to easure the generalization error. Don't tweak your model after measuring the generalization error: you would just start overfitting the test set.

## Present your solution

- [] Document what you have done.
- [] Create a nice presentation. Make sure you highlight the big picture first.
- [] Explain why your solution achieves the practical/business objective.
- Present interesting points you noticed along the way:
	- [] Describe what worked and what did not.
	- [] List your assumptions and your system's limitations.
- [] Ensure your key findings are are communicated through effective visualizations and/or easy to remember statements (e.g. "the median income is the number-one predictor of housing prices").

## Launch your system

- [] Get your solution ready for production (plug into production data inputs, write unit tests, etc.).
- [] Write monitoring code to check your system's live performance at regular intervals and trigger alerts when it drops.
	- Beware of slow degradation: models tend to "rot" as data evolves.
	- Measuring performance may require a human pipeline (e.g. via crowdsourcing service).
	- Also monitor your inputs' quality (e.g., a malfunctioning sensor sending random values, or another team's output becoming stale). This is particularly important for online learning systems.
- [] Retrain your model on a regular basis on fresh data (automate as much as possible).



