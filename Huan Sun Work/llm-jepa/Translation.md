Project Idea:
- Use JEPA training on translation pairs to make better multi-lingual models
- If translational pairs can work well with JEPA, use auto-translation during pre-training for better general models

Steps to enact:
- Find dataset (WMT or FLORES)
- Figure out datasize
- Figure out dataloading
	- How to form message (add directional prefix or no)
- Figure out finetuning strategy (Full vs LoRa)
- Finetune model and confirm model performance
	- Translational accuracy on WMT and FLORES validation sets
	- Visualize representations of chinese and english pairs, T-SNE
	- Test performance on chinese reasoning/other non-translational tasks
	- Test transfer learning

Thoughts:
- If generalized translation of english to other languages and aligning does not present benefits, perhaps anytime non-english data appears in training, using JEPA to align it with english data will result in better multi-lingual models