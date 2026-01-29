How can we assure that our models are reliable, secure, and fair?

**Hallucinations**
For reliability, we are concerned with models hallucinating. This can mean a range of different things from outputting gibberish in small models to fabricating believable lies in bigger models.

Here are a few of the mechanisms that lead to hallucinations:
- Somewhat known subjects, but incomplete info
	- If a model has some recognition of the topic, but not full information, sometimes they will fill in the gaps with believable information.
- Model not knowing when to stop
	- Sometimes, often in small models, they have a hard time stopping at the right time so they generate gibberish or repetitive text
- Non-consistent responses
	- This occurs where models generate information that contradicts either the prompt and given task or the information within its own generation.

There are a couple of reasons for hallucinations:
- Data quality
	- When data is bad or incomplete, they can lead models to generate artifacts that don't align with what we would like.
- Generation method
	- The probabilistic generation could favor more vague, high probability output leading to undesired text at times.
- Input context
	- The context we give models can either help guide the model toward what we want it to generate, or mislead generation to hallucinations.

With this, how can we minimize hallucinations?
- Clear and specific prompts
	- The easiest way to deal with hallucinations is to have razor sharp, precise prompts that put 'guide rails' on what the prompt outputs.
	- Using few-shot prompting here we can properly align it with specific task requirements.
- Formatted output
	- In addition to asking for specific formatting, some commercial LLMs have formatted response requests which allow you to assert a response fits a certain format for succesful requests.
- Active Mitigation:
	- We can augment the generation hyperparameters like temperature, top-p, repeat-penalty, etc. This allows more granular control over inference time generation which could potentially stop hallucination.
	- This is mostly useful to stop models from producing gibberish or irrelevant fluff.

Even with those actions in play, we might still see hallucination. If so, how can we detect these?

For detection/classification models:
- Monitor what classifications/confidence scores are expected
- If a classification that is unexpected is made, then flag for manual review
- Attempt to figure out why that detection occurred and address it

For generative models, it really depends on the task. For chatbots, if you want to prevent irrelevant information or factual hallucinations, you can have output be monitored via metrics that measure likelihood/consistency. For models that are built to perform tasks, you can have detection guidlines that alert whenever an unseen, or abnormal detection pattern is found. This could be rule based or one could train and ML algorithm for detecting abnormalities (logistic regression for simple things, random forest or k-nn for more complex, or LSTM/autoencoders for most complex).

**Jailbreaking**
When we are concerned with model security, we need to consider jailbreaking.

This is when an actor, often malicious, uses an array of techniques to try and persuade the model to perform a certain way. This could be leaking specific data, performing a task incorrectly, or creating some malicious code artifact.

Jailbreaking is quite serious and often needs intentional design to prevent.

Preventing these jailbreaks often comes with a safety/quality check for inputs prior to letting the model operate on them. This can look like rule-based checks for hidden text, or ML algorithms for detecting adversarial attacks on CV models.

**Biases**
It is well documented that models have biases. These biases are a result of the data models are trained on. This can look like detection differences of demographics in CV models, or positional biases in generative based ranking systems.

However they may occur, it is important to eliminate biases whenever needed.

First, how do we detect biases? This is typically done by evaluating model performance on two groups divided upon the bias being analyzed. This would be something like analyzing detection performance on images of black individuals vs white individuals. Doing this at appropriate scale and detecting significant differences is reason to suspect biases.

This can be taken even further by analyzing specific features within models using mech-interp techniques, although this is usually overkill.

Now to prevent biases once one is detected:
- Analyze the data:
	- Is the dataset biased?
		- Is it feasible to create an unbiased dataset?
	- Is their an aspect of the data that is fundamental and cannot be changed?
		- Is it possible to address or transform these fundamental features?

By asking the above questions you can get at the root cause of the biases and start to address or accept them.