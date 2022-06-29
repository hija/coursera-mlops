# Neural Architecture Search
Neural architecture search (NAS) is is a technique for automating the design of artificial neural networks.

* Automating hyperparameter (parameters set before launching the learning process, e.g. number of layers) tuning
* Tool: https://keras.io/keras_tuner/

## AutoML
AutoML automates the development of ML models

Strategies:
* Grid Search
* Random Search
* Bayesian Optimization -- Assumes that a specific probability distribution, is underlying the performance.
* Evolutionary Algorithms
* Reinforcement Learning

Performance Estimation Strategies
* Lower fidelity estimates: Train on a subset, lower res or smaller NN (--> Bad, as research has shown)
* Learning Curve Extrapolation: Try to extrapolate the learning curve, remove bad performance as early as possible
* Weight Inheritance/Network Morphisms: Similar to transfer learning