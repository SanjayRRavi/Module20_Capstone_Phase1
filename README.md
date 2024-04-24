### Project Title
Anomaly Detection using Machine Learning (ML) Models to Accelerate Bug Finding During Validation

**Author**

Sanjay Ravi

#### Executive summary
This research work addresses the problem of anomaly detection during hardware/system validation, which involves how to accelerate bug finding through models that predict if a test sequence is normal or anomalous.  A few machine learning (ML) classfication models were created, tested, and compared against each other in order to determine how accurately these models would predict anomalies.  So far, these models have been showing prediction accuracy of 94%, with the drawback of high false predictions of normal test sequences.  One of these models has been able to identify the most important token ID's for the validation teams to investigate for debugging these anomalies and to root cause the source of the problem.

#### Rationale
Without answering the research question below, the hardware/system validation teams will not be able to identify anomalies or bugs quickly, and also will not be able to gain quick insights into what types of sequences or patterns cause these anomalies or bugs to occur within the hardware/system.  This will slow down the debugging required to ship the product out the door to the customer, negatively impacting the hardware business.

#### Research Question
How do we find anomalies during hardware or hardware/software system validation in order to accelerate bug finding for faster time-to-market?

#### Data Sources
Data source is related to LogBERT-HDFS from Github:
https://github.com/HelenGuohx/logbert

#### Methodology
Scripts from the Github link above were used to create the dataset with the test sequences containing lists of token IDs.  Then unsupervised machine learning was used to create the normal and anomaly labels, since in the real world the dataset to create the models from might not have pre-defined class labels.  Then natural language processing (NLP) based feature extraction was done to process the dataset so that it could be consumed by the ML models.  Initially, 2 standard classification algorithms were used to validate the prediction capability.  Future plan is to use a neural network to validate whether or not the prediction capabilities improve compared to the 2 standard classification models.

Results will be how good the prediction is, using the test portion of the dataset, which will predict what types of sequences in the hardware/system validation will be normal and which will be anomalous.

#### Results
The summary of results are:
* Both Decision Tree and Logistic Regression have equal and high test accuracy (94% accuracy).
* For both models, precision is high but recall is low. This means that false predictions of anomalies is low, but false predictions of normal is high.
* Main advantage of Decision Tree model is the speed, where mean fit time is less.
* Recommendation would be to use the Logistic Regression model, since this has higher precision score.
* The most importance features to analyze while debugging the anomalies are these token IDs
    * token ID 16
    * token ID 26
    * token ID 44
    * token ID 38
    * token ID 25

#### Next steps
* Further work needs to be done to find a model which improves the recall score without making the precision score signifantly worse.  Exploration of neural network is part of the future plans.
* Important for the system validation user to check for the words or tokens corresponding to the above token IDs within the original logfile in order to debug the source of the anomalies or bugs.

#### Outline of project

- Link to Jupyter Notebook: (intermediate results with Decision Tree and Logistic Regression)
https://github.com/SanjayRRavi/Module20_Capstone_Phase1/blob/main/Capstone_Phase1.ipynb


##### Contact and Further Information

Sanjay Ravi

email: sanjay.ravi1975@gmail.com


