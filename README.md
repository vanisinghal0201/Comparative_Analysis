# COMPARATIVE ANALYSIS OF OVERSAMPLING TECHNIQUES ON IMBALANCED DATA
# INTRODUCTION 
Training a machine learning model on an imbalanced dataset can introduce unique challenges to the learning problem. Imbalanced data typically refers to a classification problem where the number of observations per class is not equally distributed; often there will be a large amount of data/observations for one class (referred to as the majority class), and much fewer observations for one or more other classes (referred to as the minority classes). 
Machine Learning algorithms tend to produce unsatisfactory classifiers when faced with imbalanced datasets. For any imbalanced data set, if the event to be predicted belongs to the minority class and the event rate is less than 5%, it is usually referred to as a rare event.
# DATA 
Aging-Related Bugs (ARBs) occur in long running systems due to error conditions caused because of accumulation of problems such as memory leakage or unreleased files and locks. Aging-Related. Bugs are hard to discover during software testing and also challenging to replicate. Automatic identification and prediction of aging related fault-prone files and classes in an object oriented system can help the software quality assurance team to optimize their testing efforts. Here, there are 5 datasets and machine learning techniques to predict aging related bugs. We conduct a series of experiments on publicly available dataset .Class imbalance and high dimensionality are the two main technical challenges in building effective predictors for aging related bugs.

# BALANCING METHODS
# 1. Class weight
One of the simplest ways to address the class imbalance is to simply provide a weight for each class which places more emphasis on the minority classes such that the end result is a classifier which can learn equally from all classes.
# 2. Oversampling
Another approach towards dealing with a class imbalance is to simply alter the dataset to remove such an imbalance. Common techniques for oversampling the minority classes are to increase the number of minority observations until we've reached a balanced dataset.
# 2.1 Random oversampling
The most naive method of oversampling is to randomly sample the minority classes and simply duplicate the sampled observations. With this technique, we are artificially reducing the variance of the dataset.
# 2.2 SMOTE
However, we can also use our existing dataset to synthetically generate new data points for the minority classes. Synthetic Minority Over-sampling Technique (SMOTE) is a technique that generates new observations by interpolating between observations in the original dataset.
For a given observation xi, a new (synthetic) observation is generated by interpolating between one of the k-nearest neighbours, xzi.
Xnew = xi+ λ (xzi − xi) xnew = xi + λ (xzi−xi)
where λ is a random number in the range [0,1][0,1]. This interpolation will create a sample on the line between xi and xzi.
 
# 2.3 ADASYN
Adaptive Synthetic (ADASYN) sampling works in a similar manner as SMOTE, however, the number of samples generated for a given xi is proportional to the number of nearby samples which do not belong to the same class as xi. Thus, ADASYN tends to focus solely on outliers when generating new synthetic training examples.
# MODELS USED
1. K Nearest Neighbors – Neighbours based classification is a type of lazy learning as it does not attempt to construct a general internal model, but simply stores instances of the training data. Classification is computed from a simple majority vote of the k nearest neighbours of each point.
2. Logistic Regression- Logistic regression is a machine learning algorithm for classification. In this algorithm, the probabilities describing the possible outcomes of a single trial are modelled using a logistic function.
3. Naïves Bayes- Naive Bayes algorithm is based on Bayes’ theorem with the assumption of independence between every pair of features. Naive Bayes classifiers work well in many real-world situations such as document classification and spam filtering.
4. Decision Tree- Given a data of attributes together with its classes, a decision tree produces a sequence of rules that can be used to classify the data. Decision Tree is simple to understand and visualise, requires little data preparation, and can handle both numerical and categorical data.
5. Random Forest- Random forest classifier is a meta-estimator that fits a number of decision trees on various sub-samples of datasets and uses average to improve the predictive accuracy of the model and controls over-fitting. The sub-sample size is always the same as the original input sample size but the samples are drawn with replacement.
6. Support Vector Machine- Support vector machine is a representation of the training data as points in space separated into categories by a clear gap that is as wide as possible. New examples are then mapped into that same space and predicted to belong to a category based on which side of the gap they fall.
7. Ridge CV- This classifier first converts the target values into {-1, 1} and then treats the problem as a regression task (multi-output regression in the multiclass case).
# OBSERVATION AND ANALYSIS 
# 1. Tuning Model
We Hypertuned every model on each dataset to find the best accuracy the model can predict. We used GridSearchCV and K-Fold to hypertune the models. We put different values of K as 5,10,15 and 20 and found out that 10 fold gave the best results compared to other folds.
# 2. Relative Comparison of Techniques
There are 5 datasets, 4 strategies for imbalance learning and 7 learning algorithms. Hence we generate 5∗4∗7 = 140 data points to compute the mean value of any imbalance learning strategy or classification algorithm. The mean AUC value i.e 0.89 of Random Over Sampler is best in comparison to the other imbalance learning strategies. The mean AUC value of SMOTE and ADAYSN are the second best with value 0.88. The mean AUC value of Class Weight is 0.58. The accuracy and f-measure value shows a same trend. According to both the f-measure value and accuracy Random Over Sampler performs best followed by SMOTE and ADASYN.
We also infer that Ridge Classifier is best and has a mean AUC value of 0.93. This is followed by Random Forest with mean AUC value of 0.83 and the mean AUC value of Decision Tree and KNN is 0.80 each. The mean AUC value of Logistic Regression and SVM is 0.79 each. Naives Bayes performs worst with mean AUC of 0.76. In-terms of f-measure, the mean f-measure value of Ridge Classifier is 0.916. The mean f-measure value of Decision Tree and Random Forest is 0.90 and 0.91 respectively which is higher than the mean f-measure value of SVM and Logistic Regression which is 0.85. Naives Bayes performs worst with mean f-measure of 0.81

# RESULTS
We presented a comparative analysis of oversampling techniques on 5 imbalance datasets of aging related bugs by applying 7 machine learning algorithms. From our project we concluded that Random Over Sampler proved to be best oversampling technique compared to others and Ridge Classifier, the best machine learning algorithm. 

