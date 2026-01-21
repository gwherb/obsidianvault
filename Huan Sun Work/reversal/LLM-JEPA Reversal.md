- Used vanilla transformer with LLM-JEPA loss objective.
- Did not see reversal generalization.
- Joint MRR = 0.0003
- 1st Token MRR = 0.0043
- 2nd Token MRR = 0.25

Why the discrepancy?
- LLM-JEPA loss likely only aligned the last token of the second sub-sequence with the pred token.
	- last token of other entity closest to pred token.
- With this, reverse relationships were not aligned, but just the last tokens of the entities (likely).
- Could do follow up by:
	- 1. removing pred token, should get better last token alignment
	- 2. add emb token onto second sub-sequence, should get lower last token alignment
- Follow ups would be unlikely to result in reversal generalization