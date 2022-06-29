# Advanced Labeling

## Semi Supervised
* Small data pool of labeled data
* Large pool of unlabeled data
* Cluster the data and assign the closest labeled datapoint to unlabeled datapoints

--> One example is Graph based Label Propagation

## Active Learning
* An algorithm decides which datapoints to label next, e.g. margin sampling: label the most "uncertain" point?
* A human annotes the datapoints
* A ML model is trained
* The algorithm from (1) decides again which datapoints to label next

## Weak supervision
* Unlabeled data, without ground-truth labels
* One or more weak supervision sources
  * A list of heuristics that can automate labeling
  * Typically provided by subject matter experts
* Noisy labels have a certain probability of being correct, not 100%

--> Snorkel!