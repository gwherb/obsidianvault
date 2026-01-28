How do we measure when a models performance drifts over time, or if the data distribution drifts over time?

We have two concepts to cover these:
1. Covariate shift
2. Concept drift

They deal with distributions changing over time.

Concept drift is when the underlying relation between input and output change.

Covariate shift is when the distribution of input changes, but the relationship of input to output stays the same. 

When we want to ensure that our models are correctly calibrated, we can use Estimated Calibration Error and reliability charts to visualize how our models predictions match up with empirical distributions.

- For reliability charts, we plot the predicted probability vs the empirical probability.
- This allows us to see if when the model predicts with some probability, the data distribution would suggest the same probability.
- The ECE is the difference between the existing relation and the ideal (linear) relation.