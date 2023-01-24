# Week 4 | Typical Structure of a Notebook, Balancing classes

Created: January 9, 2023 1:17 PM

# Typical Structure of a Notebook

## Tables of contents

![Untitled](Week%204%20Typical%20Structure%20of%20a%20Notebook,%20Balancing%20%20a8f0c9aeaf6a4118a46c8427bdeb2d39/Untitled.png)

In this part of the lesson, we were discussing the following Notebook structure and content: [https://www.kaggle.com/czaacza/breast-cancer-wisconsin-binary-classifier/](https://www.kaggle.com/czaacza/breast-cancer-wisconsin-binary-classifier/)

# Balancing classes

If we have imbalanced classes in our dataset (e.g: there are way more non-disease cases than disease cases), we can balance them using external libraries such as ****************imblearn**************** library.

******************Remember!******************

We should resample only the ******************training data****************** and not the testing data.

```python
random_sampler = RandomOverSampler()
features_resampled, labels_resampled = random_sampler.fit_resample(features, labels)

print('Resampled data')
print(f'Disease cases: {sum(labels_resampled):8d}')
print(f'Healthy cases: {sum(~labels_resampled):8d}')
```

```
Resampled data
Disease cases:   229787
Healthy cases:   229787
```

More: 

[https://www.kaggle.com/code/czaacza/balancing-classes](https://www.kaggle.com/code/czaacza/balancing-classes)

[https://imbalanced-learn.org/stable/over_sampling.html](https://imbalanced-learn.org/stable/over_sampling.html)