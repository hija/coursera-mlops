# Collecting, Labeling, and Validating Data

* Broken data is the most common cause of problems in production ML systems (Uber)
* No other activity in the ML life cycle has a higher ROI than improving data (Gojek)

## Research ML vs Production ML

| Criteria            | Research ML                 | Production ML                         |
| ------------------- | --------------------------- | ------------------------------------- |
| Data                | Static                      | Dynamic - Shifting                    |
| Priority for design | Highest overall accuracy    | Fast inference, good interpretability |
| Model training      | Optimal tuning and training | Coniniously assess and retrain        |
| Fairness            | Very important              | Crucial                               |
| Challenge           | High accuracy algorithm     | Entire system                         |

--> Production ML = ML + Software Engineering

## ML Pipelines
* ML pipeline workflows are usually Directed Acyclic Graphs (DAGs) 
* Example from TensorFlow Extended (TFX): Data Ingestion -> Data Validataion -> Feature Engineering -> Train Model -> Validate Model -> Push if good -> Serve Model
* Aim: Automate, monitor and maintin end-to-end ML process
* Alternatives to TFX: Airflow, Argo, Celery, Luigi, Kubeflow

## Importance of Data
* Data is a "first class citizen", i.e. very important
* Machine learning is not magic, but rather depended on very good data: Maximize predictive content, remove non-informative data and ensure feature space coverage
* Garbage In, Garbage Out

* *Feature Engineering* helps to maximize the predictive signals
* *Feaure selection* helps to measure the predictive signals

## Responsible Data
* Source Data Responsibility: Be aware if you do web scratching or using an open source dataset (e.g. Boston Dataset)
* Comply with regulations, such as GDPR
* Different kinds of harms:
  * **Representational harm** -- System amplifies or reflects negative stereotypes about particular groups
  * **Opportunity denial** -- System makes predictions and decisions that have real-life consequences and lasting impacts on individuals' access to opportunities, resources, and overall quality of life
  * **Disproportionate product failure** -- A product doesn't work or gives skewed outputs more frequently for certain groups of users
  * **Harm by disadvantage** -- System infers disadvantegous associations between certain demographic characteristics and user behaviors or interests

--> Commit to fairness!

## Changes in data

* Easy Problems: **Ground truth changes slowly** (months, years)
  * Model retraining driven by:
    * Model improvements, better data
    * Changes in software and/or systems
  * Labeling
    * Curated datasets
    * Crowd-based
  * Example: Image classification with animals
* Harder problems: **Ground truth changes faster**, i.e. weekly
  * Model retraining driven by:
    * Declining model performance
    * Model improvements, better data
    * Changes in software and/or system
  * Labeling
    * Direct feedback (e.g. see if shop item recommendations are good or not)
    * Crows-based
  * Example:  Shoe recommendations in an online store (style changes over time)
* Really hard problems: Ground truth changes very fast (daily, hourly or even minuetly)
  * Model retraining driven by:
    * Declining model performance
    * Model improvements, better data
    * Changes in software and/or system
  * Labeling
    * Direct feedback (e.g. see if shop item recommendations are good or not)
    * Weak supervision
  * Example:  Stock market

## Process Feedback and Human Labeling
**Direct (or "Process") Feedback**: We observe what actually happens vs. what we predicted should happen (e.g. in a clickstream we observe on which item is being clicked vs what we predicted).

Example Tools: Logstash, Fluentd

**Human Labeling**: A human labels data

## Detecting Data Issues

* **Drift**: Changes in data over times, such as data collected once a day

* **Skew**: Difference between two static versions, or different sources, such as training set and serving set
  
--> Good overview: https://towardsdatascience.com/understanding-dataset-shift-f2a5a262a766



