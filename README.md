# Machine-Learning-In-Medicine
**Extended Abstract**

The predictions of disease classes using genetic microarray data is presented and discussed in this repository. The predictions of disease classes using genetic microarray data is presented and discussed in this resipotory. The predictions have been carried out with the aid of naïve Bayes (NB), decision tree (DT), k nearest neighbor (kNN), artificial neural network (ANN), random forest (RF), and adaptive boosting (AdaBoost). 

The quest to develop a method that uses genetic data for disease classification has led to the application of different theoretical approaches. Based on the ability of a machine to learn and arrive at reasonable conclusions from data, this research employs machine learning models to train on measured disease class values of all samples in the genetic microarray data, with the goal of predicting disease class values of samples that have not been measured.

The genetic microarray data comprises of 63 samples. These samples have been trained using naïve Bayes (NB), decision tree (DT), k nearest neighbor (kNN), artificial neural network (ANN), random forest (RF), and adaptive boosting (AdaBoost). The 63 samples were split into 5 folds of train and validation sets with the aid of scikit-learn stratified k-fold cross-evaluation (SKF), which is a library for machine learning in python.

In order to compare the agreement between the predicted and measured disease class values, the accuracy has been evaluated using the formula:

\mathrm{Accuracy}=\frac{TP+TN}{TP+TN+FP+FN}\ 							     
where TP=\ number of correctly predicted positive values,
TN= number of correctly predicted negative values,
FP=\ number of wrongly predicted positive values,
FN=\ number of wrongly predicted negative values.

Since the training data has been split into train and validation datasets using stratified k-fold, the tuned models have been trained on the train dataset, and their performance have been tested on the validation dataset. However, Table 1 shows the accuracy values between the measured disease class values of all samples in the train dataset and the predicted disease class values of the same train data. The reason for testing on the train data is to check if the models are overfitting or underfitting the data. The default setting for NB, DT, kNN, ANN, RF and AdaBoost models have been employed. It can be observed that the accuracy value obtained from DT and RF models were the highest, followed by ANN, kNN, NB, AdaBoost had the lowest value. This hints us that the DT and RF models might be suffering a bit from overfitting. 

Table 1:	The accuracy values between the measured and predicted disease class for all samples in the train dataset using NB, DT, kNN, ANN, RF and AdaBoost models at default setting.
Models	Accuracy
NB	0.8036
DT	1.0000
kNN	0.9107
ANN	0.9643
RF	1.0000
AdaBoost	0.6607

Table 2 shows the accuracy values between the measured disease class values of all samples in the validation dataset and the predicted disease class values using the default setting for NB, DT, kNN, ANN, RF and AdaBoost models. ANN had the highest accuracy value without tuning, this is to be expected as ANN is a neural network. We recall that the DT and RF models overfit the train data in Table 1, so it is not surprising we are getting an unsatisfactory performance from these models. This should not be cause for alarm, as it is well known that DT and RF models have high tendency to overfit a dataset. This problem can be tackled by tuning some hyperparameters in these models.

Table 2:	The accuracy values between the measure and predicted disease class for all samples in the validation dataset using NB, DT, kNN, ANN, RF and AdaBoost models at default setting.
Models	Accuracy
NB	0.8462
DT	0.6923
kNN	0.7692
ANN	0.9643
RF	0.8462
AdaBoost	0.7692

To improve the accuracy of the models in Table 1, the machine learning models have been tuned. For the Naïve Bayes model (NB), the number of estimators hyperparameter has been tuned. For the decision tree model (DT), the minimum samples split, minimum samples leaf, maximum leaf nodes, maximum depth hyperparameters have been tuned. For the k nearest neighbor model (kNN), the number of neighbors and weights hyperparameters have been tuned. For the artificial neural network model (ANN), the batch size hyperparameter has been tuned. For the random forest model (RF), the number of estimators hyperparameter has been tuned. For the adaptive boosting model (AdaBoost), the learning rate, algorithm, and number of estimators have been tuned. The tuned models have been trained using the train dataset, and then been used to make predictions on the train data.

Table 3 shows the accuracy values between the measured disease class values of all samples in the train dataset and the predicted disease class values using tuned NB, DT, kNN, ANN, RF and AdaBoost models. Improvements were observed from the models after tuning. AdaBoost had a perfect score after been tuned, kNN also improved. However, DT, RF, ANN, NB accuracy score remained the same after tuning. 

Table 3:	The accuracy values between the measured and predicted disease class for all samples in the train dataset using tuned NB, DT, kNN, ANN, RF and AdaBoost models.
Models	Accuracy
NB	0.8036
DT	1.0000
kNN	0.9286
ANN	0.9643
RF	1.0000
AdaBoost	1.0000

Table 4 shows the accuracy values between the measured disease class values of all samples in the genetic microarray data and the predicted disease class values using tuned NB, DT, kNN, ANN, RF and AdaBoost models. It is observed that after tuning the DT and RF model, the problem of overfitting has been tackled, as the performance of these models on the validation dataset has improved dramatically. Improvements were observed from the models after tuning. The accuracy of the kNN and AdaBoost model on the validation dataset also improved. The NB model saw no improvements.

Table 4:	The accuracy values between the measured and predicted disease class for all samples in the validation dataset using tuned NB, DT, kNN, ANN, RF and AdaBoost models.
Models	Accuracy
NB	0.8462
DT	0.9231
kNN	0.9231
ANN	0.9231
RF	0.9231
AdaBoost	0.8462

**Conclusion**

In this study, the disease classes of some patients with 7070 recorded genes each have been predicted using naïve Bayes (NB), decision tree (DT), k nearest neighbor (kNN), artificial neural network (ANN), random forest (RF), and adaptive boosting (AdaBoost) models. When compared with the actual class data, all models are found to give very good predictions of the disease classes. With an accuracy of 0.9231, the kNN, DT, RF, and ANN models are found to perform very well on the validation data, However, when the predicted values are compared with the actual class values, the ANN predicted values were most in agreement with the actual values. This study concludes that the disease classes given the patient genes can successfully be predicted using ANN, kNN, DT and RF.
