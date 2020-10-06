# COMP472
Artificial Intelligence

# Team Members
* Avkash Sharma
* Karthikan Jeyabalan (40032932)
* Nirusan Nadarajah

# Wiki
## Python
`pip install jupyterlab` install jupyter
`pip install -U scikit-learn` install scikit-learn

once installed, clone the repo and open terminal to cloned directory

`jupyter notebook` runs jupyter

## Conda
`conda install -c conda-forge notebook` install jupyter
`conda install scikit-learn` install scikit-learn

# 1 Experiments with Machine Learning
## 1.1 scikit-learn
For this assignment, you will use the scikit-learn machine learning framework to experiment with different machine learning algorithms and different data sets. The focus of this assignment lies more on the experimentations and analysis than on the implementation. scikit-learn is an open-source machine learning library for Python (see http://scikit-learn.org/stable/), which provides an interface to program with a variety of different algorithms and built-in datasets. There are plenty of online documentation and examples of code online.
## 1.2 Data Sets
You must use the 2 datasets provided on Moodle (see the zip file DataSet-Release1). Both datasets are about
the classification of black & white images of size 32 × 32 that represent a character. For example, the image
represents the character ‘A’.
Dataset 1 contains images of the 26 uppercase letters [A – Z].
Dataset 2 contains images of 10 Greek letters.

Each dataset is in .csv format, where each row is a data instance. Each instance is composed of 1024 binary
features followed by its class (the index). Each dataset contains 3 splits:
- training: to be used for training your models.
- validation: to be used for validating/experimenting with your models.
- test: to be used to report your final output.

## 2 Your Task
For each dataset, write the necessary code to:
1. Plot the distribution of the number of the instances in each class.
2. Run 6 different ML models:
(a) GNB: a Gaussian Naive Bayes Classifier, with default parameter values.
(b) Base-DT: a baseline Decision Tree using entropy as decision criterion and using default values values
for the rest of the parameters.
(c) Best-DT: a better performing Decision Tree found by performing grid search to find the best combination of hyper-parameters. For this, you need to experiment with the following parameter values:
- splitting criterion: gini and entropy
- maximum depth of the tree: 10 and no maximum
- minimum number of samples to split an internal node: experiment with values of your choice
- minimum impurity decrease: experiment with values of your choice
- class weight: None and balanced
(d) PER: a Perceptron, with default parameter values..
(e) Base-MLP: a baseline Multi-Layered Perceptron with 1 hidden layer of100 neurons, sigmoid/logistic
as activation function, stochastic gradient descent, and default values for the rest of the parameters.
(f) Best-MLP: a better performing Multi-Layered Perceptron found by performing grid search to find the
best combination of hyper-parameters. For this, you need to experiment with the following parameter
values:
- activation function: sigmoid, tanh, relu and identity
- 2 network architectures of your choice: for eg 2 hidden layers with 30+50 nodes, 3 hidden layers
with 10+10
- solver: Adam and stochastic gradient descent
## 3. For each model and each dataset, write the necessary code to generate a csv (comma separated values)
output file that contains the output classification and the performance of each model for each dataset. This
output file should be named [model name]-[dataset].csv. Therefore you should generate 12 files:
GNB-DS1 Base-DT-DS1 Best-DT-DS1 PER-DS1 Base-MLP-DS1 Best-MLP-DS1
GNB-DS1 Base-DT-DS2 Best-DT-DS1 PER-DS1 Base-MLP-DS2 Best-MLP-DS2
These files should contain:
* the row number of the instance, followed by a comma, followed by the index of the predicted class of
that instance, as in:
1,24 // if your model’s predicted class for instance 1 is 24 (Y)
2,25 // if your model’s predicted class for instance 2 is 25 (Z)
3,4 // if your model’s predicted class for instance 3 is 4 (E)
* a plot the confusion matrix
* the precision, recall, and f1-measure for each class
* the accuracy, macro-average f1 and weighted-average f1 of the model
