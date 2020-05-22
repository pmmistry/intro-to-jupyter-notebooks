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

## Workshop 

### Prerequisites

* An [IBM Cloud Account](https://cloud.ibm.com)
* An account on [IBM Watson Studio](https://dataplatform.cloud.ibm.com/).

### Steps

#### Step 1 : Setup project and data in Watson Studio 
To complete this code pattern we'll need to do a few setup steps before creating our model. In Watson Studio we need to: create a project, add our patient data (which our model will be based on), upload our notebook, and provision a Watson Machine Learning service.

#### 1.1. Create a project in Watson Studio

* Log into IBM's [Watson Studio](https://dataplatform.cloud.ibm.com). Once in, you'll land on the dashboard.

* Create a new project by clicking `+ New project` and choosing `Data Science`:

   ![studio project](https://raw.githubusercontent.com/IBM/pattern-utils/master/watson-studio/new-project-data-science.png)

* Enter a name for the project name and click `Create`.

> **NOTE**: By creating a project in Watson Studio a free tier `Object Storage` service will be created in your IBM Cloud account. Select the `Free` storage type to avoid fees.

#### 1.2 Add patient data as an asset

The data used in this example was generated using a normal distribution. Attributes such as age, gender, heartrate, minutes of exercise per week, and cholesterol are used to create the model we will eventually deploy.

* From the new project `Overview` panel, click `+ Add to project` on the top right and choose the `Data` asset type.

   ![add asset](https://github.com/IBM/pattern-utils/raw/master/watson-studio/add-assets-data.png)

* A panel on the right of the screen will appear to assit you in uploading data. Follow the numbered steps in the image below.

  * Ensure you're on the `Load` tab. [1]
  * Click on the `browse` option. From your machine, browse to the location of the [`patientdataV6.csv`](data/patientdataV6.csv) file in this repository, and upload it. [not numbered]
  * Once uploaded, go to the `Files` tab. [2]
  * Ensure the `patientdataV6.csv` appears. [3]

   ![add patient data](https://github.com/IBM/pattern-utils/raw/master/watson-studio/data-add-data-asset.png)

* **TIP:** Once successfully uploaded, the file should appear in the `Data assets` section of the `Assets` tab.

![data asset](https://github.com/IBM/predictive-model-on-watson-ml/blob/master/doc/source/images/data-asset.png)

#### 1.3 Provision a Watson Machine Learning service

* Click on the navigation menu on the left (`☰`) to show additional options. Click on the `Watson Services` option.

   ![add asset](https://github.com/IBM/pattern-utils/raw/master/watson-studio/hamburger-menu-watson.png)

* From the overview page, click `+ Add service` on the top right and choose the `Machine Learning` service. Select the `Lite` plan to avoid fees.

* Once provisioned, you should see the service listed in the `Watson Services` overview page. **Select the service by opening the link in a new tab.**  We're now in the IBM Cloud tool, where we will create service credentials for our now Watson Machine Learning service. Follow the numbered steps in the image below. **We'll be using these credentials in Step 2, so keep them handy!**.

   ![wml credentials](https://github.com/IBM/pattern-utils/raw/master/watson-studio/credentials-wml.png)

* **TIP:** You can now go back the project via the navigation menu on the left (`☰`).

   ![add asset](https://github.com/IBM/pattern-utils/raw/master/watson-studio/hamburger-menu-project.png)

#### 1.4 Create a notebook in Watson Studio

The notebook we'll be using can be viewed in [`notebooks/predictiveModel.ipynb`](notebooks/predictiveModel.ipynb), and a completed version can be found in [`examples/exampleOutput.ipynb`](examples/exampleOutput.ipynb).

* From the new project `Overview` panel, click `+ Add to project` on the top right and choose the `Notebook` asset type. Fill in the following information:

  * Select the `From URL` tab. [1]
  * Enter a `Name` for the notebook and optionally a description. [2]
  * Under `Notebook URL` provide the following url: `https://github.com/pmmistry/intro-to-jupyter-notebooks/blob/master/notebooks/intro-to-predictive-modeling.ipynb`[3]

  * For `Runtime` select the `Default Spark 2.3 & Python 3.6` option. [4]

  ![add notebook](https://github.com/IBM/pattern-utils/raw/master/watson-studio/notebook-create-url-spark-py36.png)

* **TIP:** Once successfully imported, the notebook should appear in the `Notebooks` section of the `Assets` tab.

  ![notebook asset](https://github.com/IBM/predictive-model-on-watson-ml/blob/master/doc/source/images/notebook-asset.png)

  







