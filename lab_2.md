# Introduction to data analysis with PixieDust 
[PixieDust](https://github.com/pixiedust/pixiedust) is an open source helper library that works as an add-on to Jupyter notebooks to improve the user experience of working with data. It also fills a gap for users who have no access to configuration files when a notebook is hosted on the cloud.

**In this lab we will use PixieDust to explore and analyze customer behavior information of a example of a same-day grocery delivery service** 

#### About the data
* [customers_orders1_opt.csv](https://github.com/IBM/analyze-customer-data-spark-pixiedust/blob/master/data/customers_orders1_opt.csv): Fictitious customer demographics and sales data. Published by IBM. Available as a data set on [Watson Studio](https://dataplatform.cloud.ibm.com/exchange/public/entry/view/f8ccaf607372882403a37d9019b3abf4)

![part_1](https://github.com/IBMDeveloperUK/pixiedust-spark-wml-workshop/blob/master/images/part_1.png)

When you have completed this workshop, you will understand how to:

- Use [Jupyter Notebooks](http://jupyter.org/) in [IBM Watson Studio](https://dataplatform.ibm.com/)
- Load data with PixieDust and clean data with Spark
- Create charts and maps with [PixieDust](https://github.com/pixiedust/pixiedust)

## Workshop 

#### Step 1 
 - Add a new notebook to your project. Click `Add to project` and choose `Notebook`:

![](https://github.com/IBMDeveloperUK/pandas-workshop/blob/master/images/addnotebook.png)

#### Step 2
- Choose new notebook `From URL`. Give your notebook a name and copy the URL : `https://github.com/pmmistry/intro-to-jupyter-notebooks/blob/master/notebooks/intro-to-pixie-dust.ipynb` 

#### Step 3 - Important 
- Select the **Default Spark 2.3 & Python 3.6** runtime and click `Create Notebook`.
 
- The notebook will load. Now you can follow along with the instructions in the notebook.

## Load customer data in the notebook

* Run the cells one at a time. Select the cell, and then press the `Play` button in the toolbar.
* Make sure the latest version of PixieDust is installed. If you get a warning run this code in a new cell: `pip install --upgrade pixiedust`. **Do not add --user as suggested by PixieDust**
* Load the data into the notebook.

## Transform the data with Apache Spark

Before analyzing the data, it needs to be cleaned and formatted. This can be done with a few [pyspark](https://spark.apache.org/docs/latest/api/python/index.html) commands:

* Select only the columns you are interested in with `df.select()`
* Convert the AGE column to a numeric data type so you can run calculations on customer age with a user defined function ([udf](https://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=udf#pyspark.sql.functions.udf)).
* Derive the gender information for each customer based on the salutation and rename the GenderCode column to GENDER with a second `udf`.

## Create charts and maps with PixieDust

The data can now be explored with PixieDust:

* With `display()` explore the data in a table.

* Then click on the below button to create one of the charts in the list.

![notebook](https://github.com/IBMDeveloperUK/pixiedust-spark-wml-workshop/blob/master/images/display.png)

* Drag and drop the variables you want to display into the `Keys` and `Values` fields. Select the aggregation from the drop-down menu and click `OK`.

* From the menu on the right of the chart you can select which renderer you want to use, where each one of them visualises the data in a different way. Other options are clustering by a variable, the size and orientation of the chart and the display of a legend. 

## References
* [Analyze historical shopping data with Spark and PixieDust in a Jupyter notebook](https://developer.ibm.com/patterns/analyze-historical-shopping-data-spark-pixiedust-jupyter-notebook/)
* [Build a machine learning recommendation engine to encourage additional purchases based on past buying behavior](https://developer.ibm.com/patterns/build-a-product-recommendation-engine-with-watson-machine-learning/)