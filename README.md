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

1. Registered Bank Marketing dataset

![1](https://user-images.githubusercontent.com/6285945/104740240-b84c6c00-576d-11eb-92f6-bc3cde26942f.png)

2. Created an AutoML experiment, in this step I have configured a compute cluster and ran an AutoML experiment on the registered Bank Marketing dataset. The following screenshots show the successfully completed AutoML run. The best model from this experiment was the VotingEnsemble with a weighted AUC score of approximately 95%

![3](https://user-images.githubusercontent.com/6285945/104740253-be424d00-576d-11eb-8543-8cc51dbee112.png)

![2](https://user-images.githubusercontent.com/6285945/104740250-bbdff300-576d-11eb-87de-1ab4609896a4.png)

![4](https://user-images.githubusercontent.com/6285945/104740261-c0a4a700-576d-11eb-8af0-e7ae1581a27a.png)

![5](https://user-images.githubusercontent.com/6285945/104740274-c39f9780-576d-11eb-9294-b69dfe50420a.png)

![6](https://user-images.githubusercontent.com/6285945/104740281-c69a8800-576d-11eb-8a27-0d2f84348ca3.png)


3. Deployed the best AutoML model (VotingEnsemble) and enabled logging and apllication insight generation using the logs.py script

![7](https://user-images.githubusercontent.com/6285945/104740287-c9957880-576d-11eb-993f-4e4cee01f5d5.png)

![8](https://user-images.githubusercontent.com/6285945/104740293-cd28ff80-576d-11eb-8863-7e041db3edb3.png)


4. Consume model using swagger - in this step I have used the swagger.json available in the Endpoints for deployed model. Swagger helps in building, documenting, and consuming RESTful web services. It also explains what types of HTTP requests that an API can consume, like POST and GET

![9](https://user-images.githubusercontent.com/6285945/104132706-127fb280-53a5-11eb-9ca8-d42e06a7aa3e.png)

![10](https://user-images.githubusercontent.com/6285945/104132709-157aa300-53a5-11eb-8a1e-adf4f2286cf0.png)

![11](https://user-images.githubusercontent.com/6285945/104132712-18759380-53a5-11eb-8770-0565e6677245.png)

![12](https://user-images.githubusercontent.com/6285945/104132716-1ad7ed80-53a5-11eb-8abd-a172ffc5d3ff.png)

The following screenshot demonstrates the output received from the deployed model by running endpoint.py against the REST API

![13](https://user-images.githubusercontent.com/6285945/104740401-eb8efb00-576d-11eb-8d6d-93f9cd4b76c7.png)

5. Publish ML pipeline - in this step I have used python SDK to create and publish an end to end pipeline

![14](https://user-images.githubusercontent.com/6285945/104740411-ef228200-576d-11eb-8882-4d34001380b6.png)

![15](https://user-images.githubusercontent.com/6285945/104740414-f184dc00-576d-11eb-8548-2fdca8a4167e.png)

![16](https://user-images.githubusercontent.com/6285945/104740424-f3e73600-576d-11eb-865b-726c71df043c.png)

![17](https://user-images.githubusercontent.com/6285945/104740433-f6499000-576d-11eb-9461-9a39d182929c.png)

![18](https://user-images.githubusercontent.com/6285945/104740445-f8abea00-576d-11eb-8f74-b3da067b3aa9.png)




## Screen Recording
[![1](https://user-images.githubusercontent.com/6285945/104132692-ff6ce280-53a4-11eb-9ce4-94f9d7b0aef9.png)](https://youtu.be/GuhpixjSE54)

