# Define and establish baseline

Problem: Labeling (Y) can be ambigious (e.g. bounding boxes)

For small data: Clean labels are critical! Go manually through the training examples and fix labels!
For big data: A good data process is critical! But: If there's a long tail of rare events (e.g. self driving cars), the input will have small data changes too!

For unstructured data: It is easier to generate new data, e.g. by means of data augmentation. Humans can label the data easily
For structured data: It is harder to obtain more data, from just seeing the features, it's harder (or even impossible) for humans to label the data


** Label consistency is key!**

--> How to improve label consistency?
1. Have multiple lavelers label the same example
2. If there is a disagreement: Discuss (e.g. with an expert) the correct definition and labeling for examples like these
3. If labelers think that the raining example does not contain enough information, consider changing x
4. Iterate until it is hard to significantly increase

--> Also add a label for uncertainty (it doesn't always have to be 0 or 1!)
--> Sometimes you need to change hardware to obtain better data, e.g. switching out a camera if even humans struggle to do the task

## Human Level Performance
* In academia, establish and beat a respectable benchmark to support publication
* Helps establish a reasonable target for a ML system
* "Prove" that ML system is superior to humans (<-- use with caution)
* Can help to identify which areas the ML system needs to improve in

Improving label consistency will increase HLP. This makes it harder for the ML system to beat HLP, however more consistent labels will also raise the performance of the ML systems. Ultimately, increasing the HLP will benefit the actual application performance.

## Obtaining data
Instead of asking: "How long it would take to obtain $m$ examples" do "How much data can we obtain in $k$ days"? --> Get into the ML cycle (Model, Data -> Training -> Error Analysis --> Model, Data ...) as quickly as possible!

How to get data?
1. Label yourself
2. Pay others to label data
3. Buy already labeled data

## POC and Production phase
Proof-of-concept: Decide if the application is workable and worth deploying (--> Don't spend too much time on data collection!)
Focus on getting the prototype to work!

Production Phase: Replicable Timeline, e.g. TensorFlow Transform, Apache Beam, Airflow, ...

**Keep track of data provenance (where it comes from) and lineage (sequence of transformation steps)**
Meta data can be useful for error analysis and keeping track of data provenance

**For skewed data use balanced(!) train test split, e.g. in sklearn**
