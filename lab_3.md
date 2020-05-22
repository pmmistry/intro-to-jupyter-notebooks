# Introduction to Predicive Modeling with Watson Machine Learning 
[IBM Watson® Machine Learning](https://www.ibm.com/cloud/machine-learning) helps data scientists and developers accelerate AI and machine-learning deployment. With its open, extensible model operation, Watson Machine Learning helps businesses simplify and harness AI at scale across any cloud. 

### In this lab we will be deploying a model to predict heart failure with Watson Machine Learning 

> **DISCLAIMER**: This application is used for demonstrative and illustrative purposes only and does not constitute an offering that has gone through regulatory review.

This code pattern can be thought of as two distinct parts:

1. A predictive model will be built using Spark within a Jupyter Notebook on IBM Watson Studio. The model is then deployed to the Watson Machine Learning service, where it can be accessed via a REST API.

2. A Node.js web app that allows a user to input some data to be scored against the previous model.

When the reader has completed this Code Pattern, they will understand how to:

* Build a predictive model within a Jupyter Notebook on Watson Studio
* Deploy the model to the IBM Watson Machine Learning service
* Via a Node.js app, score some data against the model via an API call to the Watson Machine Learning service





