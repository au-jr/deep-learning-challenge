# deep-learning-challenge

# Module 21 - Deep Learning Challenge
### Robertson, J

## Overview of the Analysis

The purpose of this analysis is to use machine learning and neural network modelling to create a binary classifier to predict outcome of fund applicants. Alphabet Soup’s business team has supplied information of more than 34,000 organisations that have received funding over the years. Within this dataset are a number of pieces of information we can use to feed the machine learning model:

- **EIN** and **NAME**—Identification columns
- **APPLICATION_TYPE**—Alphabet Soup application type
- **AFFILIATION**—Affiliated sector of industry
- **CLASSIFICATION**—Government organisation classification
- **USE_CASE**—Use case for funding
- **ORGANIZATION**—Organisation type
- **STATUS**—Active status
- **INCOME_AMT**—Income classification
- **SPECIAL_CONSIDERATIONS**—Special considerations for application
- **ASK_AMT**—Funding amount requested
- **IS_SUCCESSFUL**—Was the money used effectively

---

## Data Processing

Information from the dataset can be classfied as either **Feature** or **Target**. 

The feature variables are the pieces of information which influence the outcomes.

The target variable is the outcome we're trying to create a model to predict.

In the initial model:

- The **Target variable** is `IS_SUCCESSFUL`.
- The **Feature variables** include `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, and `ASK_AMT`. 
  
- **Variables removed:** The `EIN` and `NAME` columns were removed from the data.

Feature data fell into a number of data categories. Neural Network Modelling is susceptible to 'overfeeding' data, which refers to feeding excessive insignificant data which oversaturates the model producing unfavourable accuracy scores.

Categorical data was grouped on elements in the category by value counts.By doing so we can group small batch data based on a cutoff count and reduce the noise/overfeeding in the model.

---

## Creating, Training, and Assessing the Model

### Initial Model

**Neurons, layers, and activation functions:** 

The model consists of three layers:
-   Input Layer:
    -   **Neurons:** 80
    -   **Activation Function:** Rectified Linear Activation (ReLU)
    -   **Input Dimensions:** Matched the shape of the feature data.

-   Hidden Layer:
    -   **Neurons:** 30
    -   **Activation Function:** Rectified Linear Activation (ReLU)
  
-   Output Layer:
    -   **Neurons:** 1
    -   **Activation Function:** Sigmoid
   

After compiling and fitting the training data we've returned a model of 53.3% accuracy with a loss of 0.8553. 

This model has failed to reach the benchmark of 75% accuracy.

### Improving the model:

The initial model was tweaked for 3 following generations in an attempt to reach the benchmark. The tweaks were as follows:

  - Dropping additional insignificant columns from the feature data.
  - Refining categorical feature cut offs to reduce the number of bins.
  - Adding more neurons to a hidden layer.
  - Adding or removing hidden layers.
  - Using different activation functions for the hidden layers.
  - Increasing or decreasing the number of epochs in the training regimen.


### Final Model

On the fourth generation the model was unable to achieve target performance of 75% accuracy. The model achieved an accuracy score of 73.15% falling just shy of the benchmark.

Multiple attempts were made to tweak the conditions more favourably to no avail. Further exploration would be required to satisfy the benchmark requirements.

The final model was as follows:

-   Input Layer:
    -   **Neurons:** 50
    -   **Activation Function:** Rectified Linear Activation (ReLU)
    -   **Input Dimensions:** Matched the shape of the feature data.

-   Hidden Layer(s):
    1. -   **Neurons:** 24
       -   **Activation Function:** Rectified Linear Activation (ReLU)
    ----
    2. -   **Neurons:** 16
       -   **Activation Function:** Rectified Linear Activation (ReLU)
    ---
    3. -   **Neurons:** 16
       -   **Activation Function:** Rectified Linear Activation (ReLU)
  
-   Output Layer:
    -   **Neurons:** 1
    -   **Activation Function:** Sigmoid

In addition to the layering tweaks, two additional feature columns were dropped, `STATUS` and `SPECIAL_CONSIDERATIONS`. These features represented an insignifcant contribution to results.

---
## Summary

Although the final model did not quite reach benchmark, the 20% improvement demonstrated significant gain in the model with relatively few tweak attempts. Further exploration and the further refinement of the same tweaking processes may produce an outcome at or exceeding benchmark.
