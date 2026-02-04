When there might be uncertainty, it is important that we can make sense of what decisions are being made. For traditional ML algorithms (regression, clustering, classification) this is relatively straightforward. However, explaining deep learning models is much more difficult. Luckily, there are tools and frameworks that can help us.

- SHAP and LIME:
	- Able to track how much individual features attribute to output
		- For continuous predictions
- Attention visualization
	- Able to visualize how certain tokens attend to others
	- Can be used on autoregressive text generation or multimodal
- Saliency Maps
	- Allows visualization of what a CNN is 'looking' at