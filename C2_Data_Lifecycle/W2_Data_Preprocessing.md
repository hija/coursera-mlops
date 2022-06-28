# Data Preprocessing / Feature Engineering

*Preprocessing Operations*

* Data Cleansing, Feature tuning, representation transformation, feature extraction, feature construction

*Feature Engineering*

* Feature Scaling (MinMax, Standardization)
* Bucketizing
* PCA, t-SNE, UMAP
* Feature Crossing (Combining multiple features, e.g. feature A + feature B)

*Challenge preprocessing data at scale*

* Difference between batch and streaming
  * Example: Feature Scaling. In batch you can calculate the mean and standard deviation for all the data (one full-pass of the data is required). In streaming, this is not possible. So you need to determine the mean and standard deviation in the training (batch) and save their values. In the prediction phase, e.g. streaming, use the saved values to do accurate feature scaling

*Tensorflow Transform* 
Implements various methods for preprocessing and feature engineering.
Cool: In training mode it analyzes the dataset (e.g. mean + standard deviation). This information is stored as a constant in the computational graph, so if you are using the model in serving mode, it uses these constants. 

## Feature selection
* Unsupervised: Remove redundant features, e.g. by looking at the correlation matrix. Highly correlated features are likely to not provide any further information to the model. Instead, they are using disk space and computational time. So you can likely remove them
* Supervised: Looks at the relationship between the features and the target variable. You can select the features which contribute most to a sucessful model / prediction and delete the ones which do not.
  * Filter Methods: Correlation, Univariate Feature Selection (SelectKBest, SelectPercentile, ...) --> Selects features based on statistical number
  * Wrapper Methods: Forward Elimination (Start with one feature, take the next "best" feature until there is no further improvement), Backward Elimination (Start with all features, drop feature one by one until the performance decreases too much), RFE (Set max number of features beforehand. Use model to select features, e.g. DecisionTreeClassifier. Discard the least useful feature. Repeat until max features number is reached)
  * Embedded Methos: Feature selection embedded in the ML algorithm, e.g. L1 regularization or Feature Imporatance in Decision Tree.