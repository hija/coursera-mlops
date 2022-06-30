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