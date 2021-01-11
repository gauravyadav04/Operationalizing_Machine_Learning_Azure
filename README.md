# Operationalizing Machine Learning

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, I have used [Bank Marketing dataset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv) to train a machine learning model using AutoML in Azure Machine Learning Studio and deploy the best model using Azure Container Instance and later consume it using REST endpoints. Also created and published a pipeline using python sdk

## Architectural Diagram

![Architecture2](https://user-images.githubusercontent.com/6285945/104144863-fe5ea400-53ea-11eb-9844-a2becbb5d837.JPG)


1. Register the Bank Marketing dataset
2. Create AutoML experiment -
   a. Create a new Standard_DS12_v2 compute cluster
   b. Configure model run by checking "Explain best model", reduce exit criterion to 1 hour, and reduce concurrency to 5
3. Select best model from AutoML experiment and deploy it using Azure Container Instance (ACI), also enable "Authentication"
4. Enable logging and application insight service for keeping track of deployed model performance and number of request handled/failed
5. Use the REST endpoint to interact with the deployed model with sample data and check its prediction results
6. Use python SDK to create a pipeline selecting the best AutoML model and publish it

## Future Work

* While running AutoML pipeline **Class Imbalance** alert was generated, this is one of the future improvements that should be implemented. We can look at different ways to combat class imbalance, such as - resampling training data, generate synthetic samples using SMOTE or the Synthetic Minority Over-sampling Technique, etc.

* Look at other performance metric such as Precision, Recall and F1 Score as Accuracy metric can be misleading while working with class imbalanced dataset 

## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

1. Register Bank Marketing dataset

![1](https://user-images.githubusercontent.com/6285945/104132692-ff6ce280-53a4-11eb-9ce4-94f9d7b0aef9.png)

2. Create an AutoML experiment

![4](https://user-images.githubusercontent.com/6285945/104132695-04ca2d00-53a5-11eb-8be3-a8ea8a7609e7.png)

![5](https://user-images.githubusercontent.com/6285945/104132699-07c51d80-53a5-11eb-8807-e553c9bdea58.png)

![6](https://user-images.githubusercontent.com/6285945/104132700-0ac00e00-53a5-11eb-8a5e-b77afce851de.png)

![7](https://user-images.githubusercontent.com/6285945/104132702-0d226800-53a5-11eb-8b4f-df5db497d03e.png)

![8](https://user-images.githubusercontent.com/6285945/104132705-0f84c200-53a5-11eb-815f-0ca5292a83ef.png)

![9](https://user-images.githubusercontent.com/6285945/104132706-127fb280-53a5-11eb-9ca8-d42e06a7aa3e.png)

![10](https://user-images.githubusercontent.com/6285945/104132709-157aa300-53a5-11eb-8a1e-adf4f2286cf0.png)

![11](https://user-images.githubusercontent.com/6285945/104132712-18759380-53a5-11eb-8770-0565e6677245.png)

![12](https://user-images.githubusercontent.com/6285945/104132716-1ad7ed80-53a5-11eb-8abd-a172ffc5d3ff.png)

![13](https://user-images.githubusercontent.com/6285945/104132717-1e6b7480-53a5-11eb-9b80-3c3e802febf4.png)

![14](https://user-images.githubusercontent.com/6285945/104132718-21666500-53a5-11eb-91e1-0dab41272370.png)

![15](https://user-images.githubusercontent.com/6285945/104132720-24615580-53a5-11eb-8725-1cf862efddaf.png)

![16](https://user-images.githubusercontent.com/6285945/104132722-26c3af80-53a5-11eb-8878-bb1234368f3a.png)

![17](https://user-images.githubusercontent.com/6285945/104132725-29bea000-53a5-11eb-9071-bfe2c5db722d.png)




## Screen Recording
[![1](https://user-images.githubusercontent.com/6285945/104132692-ff6ce280-53a4-11eb-9ce4-94f9d7b0aef9.png)](https://youtu.be/GuhpixjSE54)

