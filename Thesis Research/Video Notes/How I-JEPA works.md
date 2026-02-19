> [!PDF|] [[I-JEPA.pdf#page=1&selection=0,0,1,40|I-JEPA, p.1]]
> > Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture

This video analyzes how JEPA works in the image domain.

To start, the motivation is to create semantically rich image representations. These representations will be beneficial for downstream tasks.
- Image gen
- Semantic similarity search
- Image classification
- Segmentation
- Detection
- Depth estimation
- etc.

We also want to train in a self supervised manner that does not require hand labeled training data.

What is a latent representation?
- Some compressed representation
	- For images, take a N x N x C image, pass it through an encoder NN to flatten to a vector

Why latent representations?
- High level intelligent operation (humans, animals) operate without considering every pixel, or retina cell stimulus.
- Want our models to not have to focus on the irrelevant surface level detail and hone in on the important details.

Previous approaches:
- Invariance based pre-training
	- Same setup, but used cropping, scaling, color shifts
	- Was unclear how well this improved abstract representations
- Generative pre-training
	- Corrupt image (adding noise or other technique)
	- Reconstruct the corrupted image (ex. diffusion)

Apparently, these approaches require more finetuning to refine latent representations for better performance in tasks like classification.

Original implementation patches images and then uses some patches to predict other patches
- Context patch (x) and target patches (y) both go through vision transformer (encoder) and then use a predictor network (vision transformer) to predict latent y. Predictor uses latent x and patch details (z).

 