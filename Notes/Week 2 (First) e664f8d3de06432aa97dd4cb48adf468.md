# Week 2 (First)

Created: January 9, 2023 1:17 PM

# Course introduction

## Schedule

- Week 2: Introduction. Tools. Case 0.
- Week 3: Datasets and Metrics. Dense Neural Networks and numerical data. Case 1 Introduction.
- Week 4: Overfitting and regularization. Typical structure of Notebook. UCI Heart disease dataset.
- Week 5: Convolutional neural networks (CNN) and image data. Preprocessing data. Case 2 Introduction.
- Week 6: Image data application continues.
- Week 7: Recurrent neural networks (RNN) and natural language processing (NLP). Case 3 Introduction.
- Week 8: (no contact teaching)
- Week 9: NLP continues.
- Week 10: Review and final exam.

## Grading

### Assessment

- Attendance and weekly reports 15 p
- Case studies 55 p
- Final exam 30 p
- Total 100 p

### Final evaluation (max. 100 p)

- 90 p >= Excellent (5/5)
- 80 p >= Very good (4/5)
- 70 p >= Good (3/5)
- 60 p >= Very satisfactory (2/5)
- 50 p >= Satisfactory (1/5)

## Tools

We’ll be using the following services in order to create our Jupyter Notebook projects.

- Google Colaboratory (Cloud service)
- Kaggle online community (Cloud service)
- Anaconda Distribution (local)

## Sources

******MUST HAVE******

A book: “Deep learning with Python” François Chollet

# Basics of neural networks

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled.png)

**Neural networks** are indeed algorithms using a lot of computational layers to map the input and output data.

**Deep learning** insists a big number of those layers used by neural networks.

Machine learning is being widely used in health technology e.g in analyzing unstructured patient data.

## Machine learning approach to solving problems

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%201.png)

In machine learning, our neural network accepts some valid input and output data pairs. Starting from random values, it slowly improves itself with every new data it is given **(training)**. 

If the data is good enough, we have a working algorithm, which then can be applied for the input data we haven’t seen before to predict its output.

## Neuron model

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%202.png)

Parameters like weights, bias are called **trainable parameters**. This means that the number or trainable parameters a neuron has equals the number of input values ( n ) + a bias ( = n + 1 ).

If we’ve gone through an entire training set, the algorithm reaches **1 epoch**. 

A network in which every neuron is connected with every neuron of the previous layer is called a ********************fully connected******************** network********************.********************

### What happens inside of the neuron?

1. All of the input values are getting multiplied by the weights and being added up.
    
    ![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%203.png)
    
2. The neuron applies an **activation function.**
    
    ![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%204.png)
    
3. The neuron passes the signal to the output layer.

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%205.png)

## Activation functions examples

### Sigmoid

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%206.png)

Outputs a value **between 0 and 1.**

### ReLU ****(Rectified Linear Unit)****

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%207.png)

Outputs a value

**0 if z < 0** 

**z if z > 0**

## Problem solving example

### Classifying handwritten digits

## Data representations

Machine learning models are all about finding appropriate representations for their input data. 

For example, if we have a color, we can encode it in the RGB format or in the HSV format. These are 2 different ****************representations**************** of the same data. In order to change all the pixels to red color, a RGB representation could me more useful, but in order to change the color’s saturation, HSV will be more useful.

The new representation of a data can solve the classification problem we’re struggling with. For example if we have a few white and black points like this and we want to predict if a new point with given coordinates is more likely to be black or white, we can change the representation of the data.

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%208.png)

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%209.png)

The new representation after changing the coordinates clearly shows us that a new point is more likely to be black if x > 0 and white if x < 0.

If instead of changing the coordinates, we wanted our program to automatically search for better representations of this data, and us the percentage of points being correctly classified as a feedback, then we would be doing machine learning.

A term “deep” in Deep Learning stands for using multiple representational layers in our machine learning models.

## Deep learning model workflow

The deep learning model is mapping its input (such as image/sound etc.) with its target (a cat/specific voice message etc.). It happens via a deep sequence of simple data transformations called ************layers************.  

Each of those layers contain their parameters called weights, which are being adjusted. The adjustment of weights is based on a feedback given by a **************************loss function**************************. This function tells us, how well the network has done on mapping a specific input with an output. The result is then given to the optimizer, who is responsible to adjust the weights values so the loss function could show a little better result with next iteration.

![Untitled](Week%202%20(First)%20e664f8d3de06432aa97dd4cb48adf468/Untitled%2010.png)