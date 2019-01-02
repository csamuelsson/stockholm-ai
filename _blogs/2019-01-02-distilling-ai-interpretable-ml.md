---
title: "Distilling AI #3: Interpretable Machine Learning" 
date: "January 2nd of 2019"
summary: "In this text we summarize an awesome Distilling AI event on the topic of Interpretable Machine Learning. It was so much fun!"
authors:
  - carl-samuelsson
  - jim-holmstrom
  - kajsa-norin
  - patrik-tran
  - egil-martinsson
---

### Defining interpretability
 
_Interpretations of interpretability implications abound_. In this text, we focus on machine learning model interpretability, defined as access to tools providing answers to a why-question that help us predict future output of a machine learning model, or that helps us evaluate a prediction from said machine learning model. Here, the latter refers to properties that complement our understanding of a prediction. E.g. knowing something about the uncertainty and stability of a model does not tell us what predictions the model will make, but it improves our understanding of how to interpret the predictions.   

Using interpretability tools to understand something about the predictions, such as uncertainty or stability, rather than making the predictions, is called a proxy task. Proxy tasks are less informative than interpretability of predictions, but are nevertheless helpful. 
 
_Interpretability tools can be exhaustive explanations of the inner workings of a model_. This is called intrinsic interpretability. A model needs to be fairly simplistic to be intrinsically interpretable, e.g. linear models and shallow decision trees. Interpretability tools can also be algorithms that predict or explain outcomes generated from a model by looking at only its inputs and generated outputs. This is called post-hoc interpretability. One example is LIME. Intrinsic interpretations are always model-specific, i.e. they work only for a given class of machine learning models (such as a linear regression model). A post-hoc machine learning model is model agnostic; it can be used on a variety of trained machine learning models.

It is worth remarking that interpretability and algorithm transparency are two different concepts. Algorithm transparency has to do with how the algorithm works. At first glance, this may resemble intrinsic interpretability; however, contratrily, algorithm transparency is data-agnostic. E.g. SGD, Stochastic Gradient Descent, is an algorithm for which the workings can be explained truthfully and conclusively. The predictions of a trained model based on an SGD algorithm, however, depend on the training data it has been fed. Defining the algorithm as untrained, and the model as the trained predictor, algorithm transparency implies interpretability of the algorithm (data-agnostic), whereas machine learning model interpretability concerns interpretability of the trained model (data-dependent). This text focuses on machine learning model interpretability.
 
Furthermore, interpretability can be local or global: It can explain or predict a single prediction or a group of predictions (local). Or, it can explain how different modules affect predictions or how the entire model makes predictions (global). The latter is pretty uncommon for complex models, implying a general trade-off between accuracy and simplicity/interpretability. Notably, this is not only true for artificial intelligence, but also for organic intelligence. Our own inner workings are quite a few orders of magnitude harder to explain/interpret than is the inner workings of, say, the average amoeba. Which also is not too different from the rest of the amoeba population, for that very reason.

For further readings on the definition of interpretability, we can recommend Molnar (2018), that treats the topic at length and from which we got a lot of inspiration.
 
### Interpretability requirements and trade offs

Interpretability is subjective. Given our definition of interpretability as tools that help us predict output or evaluate a prediction, “us” is a critical component of interpretability. As comprehensibility depends on the social setting and the competence of the “interpreter”, requirements of interpretability need to relate to a specific target group. Who needs to understand the model? The programmer? The user? Customer support? We (the writers) tend to lean towards the generalisation that “local, laypersons’ interpretability” is required when explanations of individual outputs are important, e.g. if an algorithm is tasked with something where individual decisions have tangible impact such as whether or not to grant someone a loan. Global interpretability, on the other hand, is more important when the model is generally used by experts, and when individual predictions are of less import than the overall patterns of predictions.    

There is generally a trade-off between accuracy and interpretability. Simpler models are easier to interpret than more complex ones. Yet, complexity is added for a reason: it tends to improve accuracy (cf. aforementioned parallel to organic intelligence). Appropriate prioritisation between the two objectivesparameters is highly situational: sometimes interpretability is hugely important, such as for the bank in the previous example to be able to explain to an angry (prospective) customer why s/he did not get a loan. But sometimes, how we got to a certain prediction is less important than the accuracy of the prediction, e.g. being able to proactively identify signs of diseases by x-rays, arguably even more desirable in parts of the world where access to radiologists is sparse.

Interpretability enables learning, both theoretically and practically. Learning enables both improvement of algorithms going forward, as well as other aspects that indirectly affect an outcome. Take medical applications. Accuracy in identification of e.g. early signs of cancer in a large patient population, at a low cost, is perhaps more pressing than interpretability in a shorter perspective to start the treatment as soon as possible.

However, the real breakthrough for medically complex diseases, like cancer, would come when doctors and radiologists are able to draw inference from the inner workings of a highly accurate model, as it might enable better preventive treatment or advice to patients. This leaves us with the notion that we might need to consult domain experts to assess how to weight interpretability against accuracy for a given task. 

The relative value of different proxy tasks is situational. Proxy tasks can imply e.g. aforementioned uncertainty and stability, or (human) comprehensibility, fidelity, representativeness, or consistency. Proxy tasks are complementary, and input on several proxy tasks implies improved interpretability in relation to input on one proxy task. However, the relative marginal value of an additional proxy task will likely differ depending on the situation. Here, domain expertise will be necessary to understand how to best prioritise for any individual problem.

Interpretability and domain knowledge enables discarding of unrealistic predictions. Correlations and causality are related concepts, but not to be confused. A machine learning model that is trained with admirable amounts of data may find and ascribe value to spurious correlations, i.e. correlations that exist in the data but have no causal relation whatsoever. (Google it - there are tonnes of more or less epic examples.) Giving domain experts access to interpretations of a model enables identification and discarding of such correlations, by e.g. removing or controlling for some inputs.

Interpretability allows humans and robots to successfully interact. Something something about asserting trust, partial automation by having human(s) in the loop, 

### Summary, conclusions, and topics for further discussion

There are numerous interpretations of both the concept and the implications of interpretability. Our discussions and this text have focused on the complexity and trade-offs related to prioritisation of interpretability, rather than to complement the current discourse around concept definition. Hence, we have employed a wide and inclusive stance as a practicable baseline for our subsequent reasoning. 

During the discussions on Dec 17th and their subsequent extension, five main themes crystallised, which themselves offer intriguing topics for further discussion: 
The subjectivity of interpretability implies that interpretability cannot be evaluated without consideration for its target group
The trade-off between interpretability and accuracy implies a trade-off between immediate results and longer term learning 
The situational nature of the relative value of interpretability and (especially) proxy tasks implies that priorities in aforementioned trade-off vary with individual tasks
The importance of domain knowledge to ensure disregard of errors implies that the target group may need to be engaged already when solving the machine learning tasks
The enabling properties of interpretability for human-robot interaction implies that interpretability may be a critical component in many industries in which humans are posed to work alongside robots for the foreseeable future

In light of above mentioned implications, we have concluded on some general guiding principles. 

In terms of prioritisation with regards to interpretability and accuracy in any individual model, i.e. #2 and #3:
