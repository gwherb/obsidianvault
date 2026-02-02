"All models are wrong, but some are useful"

We know that models are not perfect, but how can we better identify the uncertainty/risk that they operate with?

We know that there is a certain amount of randomness when it comes to training ML models, and this can come from multiple sources:
- Data distribution
- Stochastic algorithms
- Quantization errors

How can we best use these models while considering the uncertainty that comes along with them? It depends on the ML technique being used, but generally:

- Confidence:
	- Predictions models, whether it be regression or classification, typically come with a confidence value along with its prediction. This confidence represents the models underlying knowledge about how the data distribution.
		- For example, in regression, when a model gives a high confidence score (small confidence band) we can say the data is tightly distributed around the prediction model at that point.
		- For classification, if a high confidence is given, we can say that for the input features, most of the data falls in the given category.
			- For CV detection specifically, if a person is detected with > .9 percent confidence, we can firmly say that the person/pose in the image which was classified closely resembles the persons in the training data.
	- For this, we can really only use these confidence outputs when we operate in data that lies within the training distribution.

- Because confidence can only handle uncertainty in the data distribution they are trained in, we need a way to measure uncertainty more generally. Options are:
	- Monte Carlo Dropout:
		- Run input with dropout at inference
			- This simulates running with slightly different models
		- If we see the data tightly align, we can say that our model has low uncertainty.
		- If we see a lot of variation, then our model has high uncertainty.
	- Ensembles:
		- Train multiple models independently, and combine predictions
			- Use different initialization, data shuffling, or even architectures
		- If we see lots of agreement, that is low uncertainty.
		- Lots of disagreement means high uncertainty.
		- Ensembling can be done with the same model as well when there is stochastic output
			- For example, I can run multiple forward passes through an LLM for classification and then do majority voting. The number of disagreements would show uncertainty.