# Create PowerAutomate

## Prerequisites

To be able to follow this tutorial, you will need:
- Access to the Power Platform, specifically PowerApps and PowerAutomate.
- An Azure Machine Learning model deployed on an Azure Container Instance. 

Obtain the endpoint by going to the Azure ML Studio, go to your real-time endpoint and copy the REST endpoint of your deployed model. Save this for later.

<img src="/media/Picture1.png" alt="drawing" width="600"/>

## Create flow in PowerAutomate

1. Go to www.powerautomate.microsoft.com and log in.
2. In the left navigation bar, click on **Create**. 
3. From the **Start from blank** options, select **Instant flow**. 
4. Give your flow a name and select **PowerApps** under **Choose how to trigger this flow**.
<img src="/media/Picture2.PNG" alt="drawing" width="600"/>

5. Add a **Next step**.
6. Search for **HTTP** and add this as a next step to your flow. 
  - Method: POST
  - URI: This should be the REST endpoint you obtained from the AML Studio.
  - Headers: 
    key: Content-Type   	value: application/json
  - Body: This should be whatever format your endpoint expects as input. Make sure that the amount of input values is correct according to the schema of the input data the model expects. In this case, our model expects to receive eight values in an object called data.
  
