# Neural Network Charity Analysis

## Table of Contents

- [Project Overview](#project-overview)
- [Results](#results)
  * [Data Preprocessing](#data-preprocessing)
  * [Compiling, Training and Evaluating the Model](#compiling--training-and-evaluating-the-model)
- [Summary](#summary)

## Project Overview

The purpose of this analysis is to analyze the impact of each donation made to Alphabet Soup Foundation and vet potential recipients to ensure the foundation's money is being used properly and effectively using deep learning neural network.

## Results

### Data Preprocessing

The following image is a snapshot of the provided dataset containing organizations that have applied for funds with information such as affliation, what the organization may need the money for, income and others.

**_Dataset_**

![Dataset](https://user-images.githubusercontent.com/86085601/140670577-9bc34336-31ba-4f55-a3d7-c75b20e77b2f.png)

- The first course of action was to drop the `EIN` and `NAME` columns.
- The `IS_SUCCESSFUL` column was picked as the target to train the network to identify organizations that have been successful.
- The features of the model are the `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS` and, `ASK_AMT`.

### Compiling, Training and Evaluating the Model

- To train the model, the number of input features was set to be the length of the scaled version of the train features.
- Two hidden layers was considered ideal for the model because of risk of potentially overtraining the model
  - The first hidden layer has 80 nodes
  - the second hidden layer has 30 nodes
  - All layers besides the output layer makes use of the Rectified Linear Unit `ReLu` activation function as it does not activate all the neurons at the same time.
  - The output layer makes use of the `sigmoid` activation function
- The model resulted in an accuracy of 60.83% which is not the most ideal even if not terrible.

To better optimize the model 
- The data preprocessing was repeated again with the `NAME` column included as a feature
  - It is possible an organization may have been accepted or rejected for multiple reasons
- When re-training, an additional layer was included as a larger amount of data has been included.
  - Having just two layers might leave the data open for under-fitting
  - The first hidden layer has 100 nodes
  - The second hidden layer has 30 nodes
  - The third hidden layer has only 10 nodes
  - All layers besides the output layer made use of the `ReLu` activation function while the output layer makes use of the `sigmoid` activatin function

## Summary

The optimized model resulted in an accuracy of 78.88% which is a big jump from 60%.

Overall, using a deep learning neuro network was a good idea in analyzing the data. To get the best model, it may be best to make use of Keras Tuner to get the best hyper parameters that would provide the most ideal accuracy.

A Random Forest Classifier model can also be performed as it is an ensemble learning technique that resembles neural network models in terms of structure and performance.

In any situation where machine learning is possible, using a logistic regression machine learning model might not be a bad idea as the main purpose is for the model to determine if funding an organization would be successful or not.



