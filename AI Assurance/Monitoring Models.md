If we want to ensure that models are performing well over time, how can we do that? What are the best practices for monitoring models over their production lifetime?

First, what are issues that can lead to model degradation or affect performance?
- When training and production conditions differ resulting in the production model having input that have a different distribution to input in training. If the model is not able to generalize to production data, this means the data is fundamentally different from the training data or the model is being overfit to the training data.
- Drift occurs leading to the model operating on fundamentally different features. As the similarity of production and training days diminishes it is likely to see model degradation.
	- This can be observed via data drift, prediction drift, and/or concept drift
- If data processing issues like hardware malfunctions occur, then we could also see model performance drop.

With those points of failure, how do we evaluate performance over time?
- Ideally, we will log prediction frequency, confidence, and quality as well as data characteristics so we can backtest whether current model performance makes sense.
- By comparing metrics temporally and according to data characteristics we can hone in on where the discrepancies may come from.
- If appropriate, one can sample the production environment and create new ground truth labels to get concrete measurements of model performance.

- For a truly robust system, data characteristics and model predictions will be logged for consistency monitoring, and occasional sampling and labeling of production signals will be done for model accuracy metrics.

- By logging data characteristics, data drift can be observed by looking at distributions of certain features.
- By logging prediction results, we can observe if prediction drift is occurring.
- By observing the two in parallel with production sampling, we can determine if concept drift is happening if data distribution is not changing, but the relationship between data and prediction is changing.

Are there ways of deploying models without taking the risk of them failing? Yes, we can smartly deploy models using techniques that minimize risk by forking over some development/inference overhead.

- Shadow Deployment
	- Here, we deploy our ML model, have it perform tasks, but don't use them for anything in production. This operation is made to grab data on how the model performs in production.
- Canary Release (A/B testing)
	- We can deploy the new model to a small percentage of users to gather info as well as get user sentiment/feedback on the new deployment.

For streamlining this process of monitoring, deployment, and retraining, we can employ MLOps tools like MLflow which allows us to monitor training, compared models, control which models are in deployment, and monitor production model metrics.