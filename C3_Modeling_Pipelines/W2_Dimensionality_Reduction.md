# Dimensionality Reduction

Previously in Data Mining:
    * Experts choose the data they want to examine
    * Experts choose features and transformations
    * Small number of features (e.g. to save disk space and computations took longer)

Today with Data Science:
    * We save almost everything (Big Data)
    * We want to squeeze the most of the data
    * Huge number of (potential) features --> It is required to choose the right ones

*About Neural Networks*: Neural networks will perform a kind of automatic feature selection, **but** that’s not as efficient as a well-designed dataset and model, because even unused parts of the consume space and compute resources. Additionally, unwanted features can still introduce unwanted noise and each feature requires infrastructure to collect, store, and manage.

--> Curse of Dimensionality + Hughes effect: The more the features, the larger the hypothesis space. If you add too many features, there models's performance can decrease (or even overfit). If you add to few features, the model can underperform.

## Dimensionality Reduction

* Manual -- Have an expert choose the best features and engineer new features.
* Algorithmic -- PCA, SVD, ICA, NMF or LDA

# Model Size Reduction (Quantization & Pruning)

Due to limitations of edge computing on IOT Devices (e.g. size, computing power) there is a need to speed up and to simplify models on these devices. Quantization and Pruning are two techniques which can help.

**Quantization**: Constraining an input from a continuous or otherwise large set of values (such as the real numbers) to a discrete set (such as the integers). Example: Reducing 24bit images to 8bit images.

Two ways to do this in tensorflow:
1.  Post-training quantization -- Appling quantization after a model has been trained fully without any quantization
2.  Quantization Aware Training -- Changing the model to use quantization aware layers, so the model is trained with quantized values.

**Pruning**: Going from a dense model to a sparse one, e.g. cut some unnecessary connections in a neural network or delete some nodes from a decision tree. Lottery Ticket Hypothesis: A randomly-initialized, dense neural network contains a subnetwork that is initialised such that — when trained in isolation — it can match the test accuracy of the original network after training for at most the same number of iterations. - Frankle & Carbin (2019, p.2)

(https://roberttlange.github.io/posts/2020/06/lottery-ticket-hypothesis/)

--> Evolving topic, can be done in tensorflow with tensorflow_model_optimization