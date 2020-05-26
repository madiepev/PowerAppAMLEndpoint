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

5. Add a **New step**.
6. Search for **HTTP** and add this as a next step to your flow. 
    - **Method**: POST
    - **URI**: This should be the REST endpoint you obtained from the AML Studio.
    - **Headers**: 
      key: Content-Type   	value: application/json
    - **Body**: This should be whatever format your endpoint expects as input. Make sure that the amount of input values is correct according to the schema of the input data the model expects. In this case, our model expects to receive eight values (a,b,c,d,e,f,g,h) in an object called data.
      `{"data": [ [ a, b, c, d, e, f, g, h ] ] } `
      Then we need to let the flow know these values are coming from the PowerApp we will create. So instead of a,b,c,... make sure to use the **Dynamic content** and **Ask in PowerApps**. You will have to do this eight times to make sure the flow understands it should take eight values from the PowerApps. It should then look like this:
      <img src="/media/Picture3.png" alt="drawing" width="600"/>
7. Add a **New step**.
8. Search for **Compose** and add this as a next step to your flow.  
9. As input, use the **Dynamic content** and choose **Body** from your HTTP output. This action should then look like this:
<img src="/media/Picture4.PNG" alt="drawing" width="600"/>

10. Add a **New step**.
11. Search for **Respond to a PowerApp or flow** and add this as a next step to your flow. 
12. Define your **output** to be called **Predictions** with the value of **Outputs** from your previous **Compose** step. Use **Dynamic content** to get the **Outputs** from the previous step. It should then look like this:
<img src="/media/Picture5.PNG" alt="drawing" width="600"/>

13. The flow is now finished. Make sure to **rename** it and **save** it so you can find and use it from the PowerApp we will create in Part 2.  
