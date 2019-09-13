# IDA-APS-Failure-prediction
## 1. Business Problem
### 1.1 Objective
The task is to device a prediction model for judging whether or not a vehicle faces imminent failure of APS system .

### 1.2 Description
The dataset consists of data collected from heavy Scania trucks in everyday usage. The Air Pressure System (APS) is a type of function used in heavy vehicles to assist braking and gear changing. The APS failure dataset consists of the daily operational sensor data from failed Scania trucks. The dataset is crucial to the manufacturer as it allows to isolate components which caused the failure.

### 1.3 Real world problem and constraints
1. Since we are provided with a dataset of failed scania trucks. The company wants to differentiate between the failure caused by the APS system and other failures. So that the reason for failure in the APS system can be detected easily and necessary changes can be made to avoid future failures. This will avoid a lot of expenses and will save time.

2. There are no latency issues.

3. Since company has kept the names of the attributes annonimized so interpretability won't be necessary.

For further details, Refer: 1) https://people.dsv.su.se/~isak-kar/IDA2016Challenge.txt
2) https://ida2016.blogs.dsv.su.se/?page_id=1387
3) https://www.researchgate.net/publication/330854331_An_Empirical_Comparison_of_Missing_Value_Imputation_Techniques_on_APS_Failure_Prediction

## 2. Machine Learning Problem
### 2.1 Data
#### 2.1.1 Data Source
Source : We can get the data from : https://archive.ics.uci.edu/ml/machine-learning-databases/00421/

#### 2.1.2 Data Overview
- The data is a csv file.
- Training data contains 171 columns.
- Number of rows in the train data are 60000.
- The test data has 16000 rows.
- Both the train data and test data have the class label column. - The data is highly imbalanced.
- The dataset has a lot of missing values.
- The data is numerical. - The datasets positive class consists of component failures for a specific component of the APS system. The negative class
consists of trucks with failures for components not related to the APS.
#### 2.2.1 Type of Machine Learning Problem
It is a binary classification problem. For the given numerical data on some attributes of failed scania trucks systems we have to predict whether the failure is caused in the APS system or not.The data we have got is highly imbalanced dataset with a lot of missing values.

### 2.2.2 Performance Metric
Here we'll be dealing with a cost function.

The cost function we have is:

    Cost = FN X 500 + FP X 10 
FN = False Negative : Number of wrongly predicted no failures in the APS system .
FP = False Positive : Number of wrongly predicted failure in the APS system .

As we can see that to penalize the False negatives the cost added by the FN's is more. We need to deal with the Sensitivity(Recall) primarily.
