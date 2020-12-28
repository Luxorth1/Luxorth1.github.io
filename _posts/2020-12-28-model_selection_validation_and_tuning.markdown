---
layout: post
title:      "Model Selection, validation and tuning"
date:       2020-12-28 20:08:49 +0000
permalink:  model_selection_validation_and_tuning
---


Selecting the appropriate model is potentially the most important portion of the machine learning engineering process. The appropriate model will allow you to extract additional information based on significant features and other metrics of success that you may be able to draw conclusions on. There are a number of models that you can test, we will go into more detail on these later. 

## Validation Set

Typically, when I am working with a larger dataset I usually split my data into 2 total train-test splits. The initial split happens prior to data cleaning and data exploration steps, I do this to have a completely untouched dataset that I can use as input data for a pipeline created later in the analysis. I will touch base on the benefits of developing a fluid pipeline later in this post.

## Baseline Models

One important practice is to have a baseline model, something light, fast and easy to use. I would recommend utilizing a Linear Regression or Logistic Regression model to have a baseline. Having a baseline will allow you to compare additional models that you test to a reliable model type. Since these models can be trained and tested pretty easily, and you can see quick results using a classfication report it gives you a fast way to determine a starting point. It will also give you a fantastic indicator if you data is cleaned properly, as well as a general determination of quality for your feature engineering.

## Batch Model Training

A slightly more advanced technique in model development is simply creating a function that trains and tests all of the models you are looking to try. This will drastically cut down on the code you need to run and will allow you to run it all at once. Fundamentally, you input a dictionary where the keys are the title of the model, and the value is the instance of the model using default hyperparameters. You can also have this function track the time, other evaluation metrics and print out a overlapping ROC curve to determine the best performing model. This function will, of course, take a long time to run, however this reduces the overall time of training each model individually.

After we use our batch model training function, we can take this a step further and add cross-validation into the mix, this allows us to dig a little bit deeper with hyperparameters. The functionality of this separate function will be generally the same, however this time we will tie in random search cross validation. This will allow us to try a bunch of hyperparameters to find what the best model may be. This one will definitely take much longer to process since we are trying numerous combinations of hyperparameters.

Once you are able to find the optimal model for your evaluation metric, you can start to use other cross-validation techniques to further increase model performance. I typically hold off grid search cross validation until I have a better idea of which model I want to work with. Cross validation will take much longer to process, however it will return the optimal model with the best hyperparameters.

## Pipelines

Pipelines are a great way to create an easy way to clean, process, and predict a dataset based on your specific steps. Prior to making a pipeline it would be best to create functions that run data through all of our preprocessing steps so we can have a clean way to input our data to our model. These best reason to create a pipeline is simply to have a reusable system where we can easily enter additional data and retrieve predictions.
