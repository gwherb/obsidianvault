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
- 