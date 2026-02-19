This video goes over LeCun's original paper detailing the JEPA architecture and its motivations.

He is asking the questions of how can we get machines to:
- learn as efficiently as humans and animals
- reason like humans
- think on different time horizons like humans

He details a high level cognitive architecture as a blue print for advanced models.

He also details the JEPA architecture.

He details a non-contrastive training paradigm (why is this non-contrastive?)

Contrastive learning:
- Push non-related images apart
- Pull related images together
- Usually needs labeled data to curate negative samples
- Sometimes, to really refine a model, we want to find negative samples that are close to our positive samples to refine the 'low energy region'
	- However, in high-dimensions, finding close samples can be difficult and refinement yields diminishing returns

Instead of using constructed or curated negative samples to refine the low energy regions, we want other pressures to be placed on the model.
- This removes the need for curating samples and avoids the curse of dimensionality