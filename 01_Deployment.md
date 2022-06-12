# Deployment 🚀

ML System = Code + Data

## Problem⁉️: Concept and Data Drift
**Concept Drift**: The relationship between X → Y changes
Example: Model to predict how many rooms your house has depending on your income, e.g. (Income / 1000) * 2. Due to inflation, this relationship changes over time, e.g. to (Income / 1000) * 1.5

**Data Drift**: New data is not represented in the trained data distribution accurately.
Example: A speech model is only trained on adult voices, thus the data distribution used to train the model contains only adult voices as well. If children want to use the speech model, the model might perform poorly

There is *gradual change* (e.g. in the concept driven data above) and *sudden shock* (e.g. during the pandemic, the online shopping behavior of many customers changed due to the lockdown. This lead to worse predictions in e.g. fraud detection systems)

... (To be continued) ...

## Deployment is partly a software engineering topic

Decision depends on:
* Batch or Realtime?
* Latency
* Security and Privacy
* ...

## Deployment Patterns 

* **Shadow Mode**: ML system and humans run in parallel, however the ML system's output is not used. Instead, the ML system's output is compared to the humans' decision to assess the performance of the ML system
* **Canary Deployment**: Roll out the new ML system to a very small fraction (e.g. 5%) and see how it performs for the 5%. If it works good, slowly ramp up the fraction (e.g. 10%) otherwise rollback to the old system.
* **Blue Green Deployment**: Old (blue) and new system (green) working in parallel. A router decides if the old or new ML system is responsible. Because both ML systems still work in parallel, it is easy to switch systems or to rollback to the old system. Can be used to implement the Canary Deployment system.

--> Think about the "Degree of Automation": Human only -> Shadow Mode -> AI assistence -> Partial automation -> Full Automation
AI assistence and Partial Automation: AI decides beforehand and a human has to do the difficult decisions (human in the loop)

## Monitoring 👀
* Brainstream what could go wrong and think about measures/statistics/metrics that can detect this problem
* Start with more metrics and decrease them if you do not need them or they become obsolete
* Examples
  * Software Metrics
    * Memory usage
    * Server load
    * Latency
  * Input Metrics (X)
    * Avg input length
    * Avg input volume
    * Num missing values
    * Avg image brightness
  * Output Metrics (Y)
    * \# times return of NULL
    * \# times user retries (e.g. could indicate (s)he was not happy with the initial result)
    * CTR
* Set thresholds and send an alarm if the threshold is crossed
* Monitor the whole pipeline (e.g. also Input data from another chip etc.)
--> ML and Deployment are **iterative processes**. 
