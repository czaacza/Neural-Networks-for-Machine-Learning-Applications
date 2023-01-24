# Week 3 | Datasets and Metrics

Created: January 9, 2023 1:17 PM

# Datasets

## What is the difference between test and validation set?

**Validation phase** - used in order to estimate how well our model has been trained and to estimate model properties. Thanks to validation phase, we tune our model.

**Application phase** (test set) - used to represent a real-world data with which we interact via our model. In this phase, we don’t make any changes in our model, we just test its accuracy.

![Untitled](Week%203%20Datasets%20and%20Metrics%20960a8084e432418e8e7287ff1cf9e7ca/Untitled.png)

## 80/20 rule

Steps

1. Split your data into training and testing (80/20).
2. Split the training data into training and validation (80/20).

Results

- Training set (64%)
    - used for training the model
- Validation set (16%)
    - used for tuning the parameters of the classifier during development
- Test set (20%)
    - used only to assess the final performance

# Metrics

## Most common metrics

Classification metrics:

- Accuracy, precision, recall, fscore
- Sensitivity and specificity
- ROC Curve and area under ROC

Methods for classification prediction results

- Confusion Matrix
- Classification Report

## Binary classifier problem metrics

How to calculate the accuracy, sensitivity and specificity of our binary classifier model? (model which tells us the answer yes/no e.g: 1 - There is a disease, 0 - there is no disease)

### Confusion (error) matrix

![Untitled](Week%203%20Datasets%20and%20Metrics%20960a8084e432418e8e7287ff1cf9e7ca/Untitled%201.png)

Calculate the confusion matrix:

1. Count how many of the cases have:d
- **True positives**
    - Diagnose = 1, Model = 1
- **False positives**
    - Diagnose = 0 , Model = 1
- **False negatives**
    - Diagnose = 1, Model = 0
- **True negatives**
    - Diagnose = 0, Model = 0

1. Arrange the counts into matrix form.
2. Add row and column sums.

![Untitled](Week%203%20Datasets%20and%20Metrics%20960a8084e432418e8e7287ff1cf9e7ca/Untitled%202.png)

![Untitled](Week%203%20Datasets%20and%20Metrics%20960a8084e432418e8e7287ff1cf9e7ca/Untitled%203.png)

**Accuracy** is also used as a statistical measure of how well a binary classification test correctly identifies or excludes a condition. That is, the accuracy is the **proportion** of **true** **results** (both true positives and true negatives) among the **total** **number** of cases examined.

**Sensitivity** (also called the true positive rate, the recall, or probability of detection)
measures the **percentage** (%) of **sick** **people** who are **correctly identified by the test** having
the condition.

**Specificity** (also called the true negative rate) measures the **percentage** (%) of **healthy**
**people**  are **correctly identified** **by the test** as not having the condition.

# Types of ML problems

**********************Regression********************** - Prediction in continuously varying number

******************************************Binary classification****************************************** - probability for class 1 or 0 as the model output.

**************************************************Multiclass classification************************************************** - probability for multiple classes as the model output

# Loss function

****************************Loss function**************************** - The quantity that will be minimized during training. It represents a measure of success for the task at hand.

********************Optimizer******************** - Determines how the network will be updated based on the loss func- tion. It implements a specific variant of stochastic gradient descent (SGD).

### For regression problems

**Mean Square Error (MSE)** is the most commonly used regression loss function. MSE is the sum of squared distances between our target variable and predicted values.

![Untitled](Week%203%20Datasets%20and%20Metrics%20960a8084e432418e8e7287ff1cf9e7ca/Untitled%204.png)

For the **binary** and **multiclass** **classifications**, we use much more advanced loss function formulas, but I’m not gonna show them in here.

Loss function **depends on the model’s trainable parameters**. 

L(w1, w2, w3, …)

## Learning with a loss function

Our machine learning model is trying to **lower** **the** **loss** **function** **result** with every iteration. Minimizing the value of the functions is being done by finding the **gradient** (derivative) of a function and detecting, how we should adjust the weights.

![Untitled](Week%203%20Datasets%20and%20Metrics%20960a8084e432418e8e7287ff1cf9e7ca/Untitled%205.png)