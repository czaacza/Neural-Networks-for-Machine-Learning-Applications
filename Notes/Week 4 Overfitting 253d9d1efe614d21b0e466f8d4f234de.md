# Week 4 | Overfitting

Created: January 23, 2023 1:11 PM

# Network parameters and problem types

The **activation** function for the output layer depends of the problem type:

- **Regression**: no activation
- **Binary classification**: sigmoid function
- **Multiclass classification**: softmax function

The choice of the **loss function** has to also be made according to the problem type.

- **Regression** - MSE (mean squared error)
- **Binary** **classification**: binary_crossentropy
- **Multiclass** **classification**: categorical_crossentropy

The **optimizer** takes care of updating the model weights as dictated by the computed gradient of the loss function. A good choice for an optimizer is **rmsprop.**

In terms of choosing network metrics, these are the suggested options:

- **Regression**: mae
- **Classification**: accuracy

# Overfitting

A bigger model (more layers and more neurons in each layer) is better in a sense that it can produce a broader range of representations. However, it is susceptible to overfitting, reproducing irrelevant features specific to the training set (with no general predictive value).

![Untitled](Week%204%20Overfitting%20253d9d1efe614d21b0e466f8d4f234de/Untitled.png)

Example of **underfitting** and **overfitting** on a linear regression problem. We don’t want to set too much polynomial variance. This changes our function’s real shape!

![Untitled](Week%204%20Overfitting%20253d9d1efe614d21b0e466f8d4f234de/Untitled%201.png)

Example of **overfitting** in a classification problem is presented on the 3rd image. Our network is taking the noise into consideration, we don’t want that!

When training our model, we have to remember **not to train it too much**. After a specific number of epochs, even though our model gains accuracy when working with training data, it will start to **lose its accuracy working with unseen** (validation) **data**! 

![Untitled](Week%204%20Overfitting%20253d9d1efe614d21b0e466f8d4f234de/Untitled%202.png)

Therefore, during the training process, we have to analyze the validation layer simultaneously. 

If our model is doing well with the training data, but worse with the validation data, it is **overfitted**!

## Fighting overfitting

Overfitting can be fought against by:

- **Adding more data**
    
    Always the best option, but usually not feasible.
    
- **Simplyfing the model**
- **Adding regularization**
- **Adding dropout**

## Adding regularization

If we want to add a penalty to our loss function, we can use **regularization**:

![Untitled](Week%204%20Overfitting%20253d9d1efe614d21b0e466f8d4f234de/Untitled%203.png)

Regularization makes our Loss function even more strict. If our neuron’s weights are going to grow, the loss function’s value is also going to **grow dramatically**. This can make our model more **sensitive** for the **weight’s** **changes**.

## Adding dropout

Another way to fight the overfitting is implementing a **************dropout**************. Dropout forces a given percentage of hidden layer neurons to give a **0 output**. The dropout neurons are being selected ****************randomly****************.

Example of a **Dropout(0,5)** (A 50% dropout - random 50% of the neurons’s outputs are set to 0) 

![Untitled](Week%204%20Overfitting%20253d9d1efe614d21b0e466f8d4f234de/Untitled%204.png)

A real master’s of Machine Learning approach is to always build our model as overfitted, so we can know the border of the model’s accuracy. Then, we can implement the ways to reduce it and make our model as good as possible.

An excellent example of overfitting can be found at my Google Colab: [https://colab.research.google.com/drive/1JrTKx3ddipJd3iKfRp2xLxPZMXE7YKcj?authuser=5#scrollTo=DUNNKhNjoz8v](https://colab.research.google.com/drive/1JrTKx3ddipJd3iKfRp2xLxPZMXE7YKcj?authuser=5#scrollTo=DUNNKhNjoz8v)