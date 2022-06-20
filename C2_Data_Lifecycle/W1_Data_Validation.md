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