How do you measure the performance of a classification model? Is it really as simple as looking at accuracy? Often times not. While accuracy can be a good measure of performance, it almost always more nuanced.

Accuracy = $\frac{TP+TN}{ALL}$

- For accuracy we are comparing how well we can correctly classify without discrepancy for class.

Precision = $\frac{TP}{TP+FP}$

- Precision concerns itself with 'when you do make the prediction of a given class, how often is it correct'
- This is more nuanced than accuracy as it is concerning the positive classification or assertion of a specific class

Recall = $\frac{TP}{TP+FN}$

- Recall is asking 'what fraction of the data that actually belongs to the class are you identifying?'
- This is more of a measure of how much of a particular class are you getting?

False positive rate = $\frac{FP}{FP+TN}$

- This is looking at how often are you incorrectly labeling a class.

These three metrics give a more granular look into model performance than accuracy alone can give. Often, there is not one good set of outcomes, but each model/project requires its own tuning for the desired level and tradeoffs.

A couple things of note:
- When wanting to identify a category that is scarce in number, often recall is very important as maximizing it ensures grabbing all the possible datapoints for a given class.
	- In this scenario, precision may be less useful
- In general, use recall when false negatives are costly, false positive rate when false positives are costly, and precision when it is important for positive predictions to be correct. Although these should always be balanced.

When balancing we want to consider:

ROC (receiver-operating characteristic) curve

- This is a visual representation of model performance across all thresholds.
- This plots the false positive rate vs the true positive rate (recall)
- Area under the curve can be used to assert how well a model does compared to random classification (0.5).

We can also look at precision-recall curves which are just visualizations for balancing the two.

For my project, it is important we maximize recall of contribution statements in extraction as we want to find as many as we can and they are not that common (~7%).