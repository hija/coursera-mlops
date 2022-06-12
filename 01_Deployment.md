# Deployment

## Problem: Concept and Data Drift
**Concept Drift**: The relationship between X → Y changes
Example: Model to predict how many rooms your house has depending on your income, e.g. (Income / 1000) * 2. Due to inflation, this relationship changes over time, e.g. to (Income / 1000) * 1.5

**Data Drift**: New data is not represented in the trained data distribution accurately.
Example: A speech model is only trained on adult voices, thus the data distribution used to train the model contains only adult voices as well. If children want to use the speech model, the model might perform poorly

There is *gradual change* (e.g. in the concept driven data above) and *sudden shock* (e.g. during the pandemic, the online shopping behavior of many customers changed due to the lockdown. This lead to worse predictions in e.g. fraud detection systems)

... (To be continued) ...
