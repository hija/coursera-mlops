# Select and train model

AI System = Data + Code

Two approaches:
* **Model centric approach** (Focus on Code): More common in university. You have the dataset fixed (a dataset you benchmark against) and you try to increase you accuracy / F1 score / ... by improving the model, e.g. the architecture, hyperparameters etc.
* **Data centric approach** (Focus on Data): More common in the industry. You have the code (e.g. model which was pretrained and downloaded from github) fixed and instead you try to increase the accuracy / F1 score / ... by improving the dataset, e.g. by data augmentation, data cleaning etc.

The paradigm behind Deep Learning is now facing a shift from model-centric to data-centric.

## Challenges in model development
 1. Doing well on training set (usually measured by average training error).
 2. Doing well on dev/test sets.
 3. Doing well on business metrics/project goals (e.g. latency, in a timely manner eg.)

Problem on (3): The "real world" can be different from the training and dev/test sets and it is important to keep recent data in the training and test data.

## Working on key slices
Make sure not to discriminate by ethnicity, gender, location, language or other protected attributes.

--> Work on a slice of the dataset with diverse gender, ethnicity, etc. and see if it performs significantly worse for any characteristic

## Baseline: Human Level Performance
| Class  | Machine Learning Model Performance | Human Level Performance | Difference |
|--------|------------------------------------|-------------------------|------------|
| Apple  | 80%                                | 90%                     | 10%        |
| Banana | 10%                                | 10%                     | 0%         |
| Orange | 70%                                | 72%                     | 2%         |

Instead of just looking at the performance of the ML model (here Banana look very bad), it is better to compare it to a baseline, e.g. a human performance.
Our first goal should be to improve to human level performance, so focusing on apple is beneficial, although we perform very good there already.

Other baselines:
* Literature
* Older system

Baseline gives an **estimate of the irreducible error** / Bayes error and **indicates what might be possible**.

## Steps for getting started
1. Literature research to see what's possible
2. Find an open source implementation
3. A reasonable algorithm with good data will often outperform a great algorithm with not so good data.

Do a sanity-check for code and algorithm: Try to overfit a small training dataset before training on a large one.

## Error analysis and performance auditing

* Look at misclassified examples
  * Give them tags (e.g. noisy background, too bright etc.)
* Then look at the tags and which tag is common
* Then try to generate more examples, e.g. with data augmentation
* Train again and start over

Useful metrics:
* What fraction of errors has that tag?
* Of all data with that tag, what fraction is misclassified?
* What fraction of all the data has that tag?
* How much room of improvement is there in that tag? 

## Prioritizing what to work on

| Class  | Machine Learning Model Performance | Human Level Performance | Difference | Percent of Data | Weighted Difference |
|--------|------------------------------------|-------------------------|------------|-----------------|---------------------|
| Apple  | 80%                                | 90%                     | 10%        | 10%             | 10% * 10% = 1%      |
| Banana | 10%                                | 10%                     | 0%         | 20%             | 0% * 20% = 0%       |
| Orange | 70%                                | 72%                     | 2%         | 70%             | 2% * 70% = 1,4%     |

Look at the difference to human performance and how important that case is, e.g. how often it occurs. Then this helps to prioritize, e.g. in this example
Orange > Apple > Banana

Other things to consider:
* How much room for improvement there is.
* How frequently that category appears.
* How easy is to improve accuracy in that category.
* How important it is to improve in that category.

## Skewed Dataset
* Look at Recall, F1, Precision

## Performance auditing
**Check for accuracy, fairness and bias.**

1. Brainstorm the ways the system might go wrong.
Look at the performance e.g. on different genders or rare classes
3. Establish metrics to assess performance against these issues on appropriate slices of data.
4. Get business/product owner buy-in.

## Grouping tags
Imagine there is an image classification task and the model performs good, but is bad with fruits. Chances are that focusing on improving one item in the group of fruits improves the overall performance of the fruit group. 

## Data Augmentation
**Create realistic examples that (i) the algorithm does poorly on, but (ii) humans (or other baseline) do well on**

## Adding data
* For unstructured data (images, voice, ...) adding data rarely hurts
* For structured data you can add new features in order to improve the performance, e.g. if there is a recommender system for restaurants which recommends restaurants with only meat-meals to vegetarians, it can be fruitful to add the feature "vegetarian" to the person's feature set and "percent-of-meatmeals" to the restaurant's dataset. Adding data only would probably not increase the performance.

## Experiment Tracking
**What to track?** Data, Code, Hyperparameters, Results
**How to track?** Textfile, Spreadsheet or experiment tracking system (start easy and improve if needed)
**Desired features** In depth analysis of results, resource monitoring, visualization etc.

--> Examples: MLFlow, DVC Studio, TensorBoard

## From Big Data to good data
Try to ensure consistently high-quality data in all phases of the ML project lifecycle.

Good data is:
* Cover of important cases (good coverage of inputs x)
* Defined consistently (definition of labels y is unambiguous)
* Has timely feedback from production data (distribution covers data drift and concept drift)
* Sized appropriately
