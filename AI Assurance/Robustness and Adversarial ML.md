How can we be sure that our models are robust? If someone tries to use the model on input designed to trick the model, what can be done?

An attack using some image meant to trick a model is called an adversarial attack.

In classification models, they are most commonly used to trick the model into misclassifying the input. This is typically done via the addition of noise into some input.

The susceptibility of a model to input with adversarial noise can be mitigated by training models with noise. Intentionally training on adversarial inputs is called adversarial training. 