# Data Journey and Data Storage

* Data Provenance == Where does the data come from? 
* Data Lineage == How has the data been modified throughout the pipeline?
* Data Versioning helps with this, e.g. DVC

## ML Metadata

* Use a Metadata store track metadata flowing between different components in the pipeline
* Relevant Metadata:
  * Artifacts: Data going as input or generated as output by a component
  * Execution:  Record of component in pipeline
  * Context: Conceptual grouping of executions and artifacts

More Info: [here](https://www.tensorflow.org/tfx/guide/mlmd)

## Schema (Development)

When generating a schema of the data, anomalies (e.g. an int value becomes a float) can be found.

* Generate two schemas (one training, one serving), e.g. to have one with the target variable and one without

## Feature Store

A feature store is a database which stores features of a dataset so that multiple models can use them instead of every model needing to calculate the feature on its own. Sometimes it offers features such as versioning. --> [https://feast.dev/](https://feast.dev/)

(+ Data Warehouse / + Data Lake)