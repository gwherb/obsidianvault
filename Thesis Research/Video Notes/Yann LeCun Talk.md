https://www.youtube.com/watch?v=yUmDRxV0krg
Yann LeCun | Self-Supervised Learning, JEPA, World Models, and the future of AI

Energy functions:
- Not necessarily an actual loss function used, but a measure of dependency/relationship between input and output. Can be loss, or relationship of input and output at infrerence.
- Energy functions describe a landscape where compatible input and output have low energy, and incompatible pairs, or things that are not trained on, have high energy
- How do we train a model such that the low energy is at and around the training samples in this landscape, and high energy away from them?
	- Method 1: just minimize comparison loss D(x,y)
		- Here, we will run into collapse as the system can learn to produce scalar values mimicking the identify function.
	- Method 2: contrastive learning
		- We use points outside of the training distribution to push energy levels higher
		- How do we get these points?
			- Hand crafted (bad)
			- Sample outside of distribution (could be bad)
		- A big problem with sampling is for high dimensional operations
			- The curse of dimensionality shows that when moving into high-dimensional spaces, the volume rapidly grows meaning that everything is far away from each other and relative distances become similar. This makes points hard to differentiate from and patterns harder to exploit.
			- This means that as dimensions grow higher, the number of contrastive points needed to alter the energy function grows exponentially, so these do not scale well.
	- Method 3: regularized methods
		- Instead of saying everything can be low or high energy, limit the amount of low energy that is available and minimize over the training distribution.
		- Forces the model to have low and high energy areas, and closely fits the training distribution.