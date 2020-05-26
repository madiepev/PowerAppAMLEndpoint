# Integrate an Azure Machine Learning endpoint in your PowerApp

In this tutorial, you will use PowerApps and PowerAutomate to quickly create an app that is using a model deployed on ACI with Azure Machine Learning. There are two parts to this tutorial:
- Part 1: Creating a PowerAutomate flow to call upon the model after we click on a button in our PowerApp
- Part 2: Creating the PowerApp to fill in the data that will be sent to the model after clicking on a button and receiving the response/prediction from the model

### Contents
This tutorial only covers how to integrate your already deployed model in PowerApps and PowerAutomate. The tutorial is based on a model that has been created and deployed in the DP-100: Designing and Implementing Data Science Solutions on Microsoft Azure course. Find the DP-100 instructions [here](https://github.com/MicrosoftLearning/DP100/tree/master/labdocs). 

If you haven't participated in the full DP-100 course, these are the labs you need to complete before you can do this tutorial:
- [Lab 1A](https://github.com/MicrosoftLearning/DP100/blob/master/labdocs/Lab01A.md)
- [Lab 1B](https://github.com/MicrosoftLearning/DP100/blob/master/labdocs/Lab01B.md): Task 1 only (installing SDK and cloning Git Repo)
- [Lab 7A](https://github.com/MicrosoftLearning/DP100/blob/master/labdocs/Lab07A.md)

### Resources
This tutorial makes use of the following technologies:
- Azure Machine Learning: 
  - [Documentation](https://docs.microsoft.com/en-us/azure/machine-learning/)
  - [Learning Path on Microsoft Learn](https://docs.microsoft.com/en-us/learn/paths/build-ai-solutions-with-azure-ml-service/)
- A deployed model on Azure Container Instances: 
  - [Documentation](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-azure-container-instance)
- Power Automate: 
  - [Documentation](https://docs.microsoft.com/en-us/power-automate/)
  - [Short introduction on Microsoft Learn](https://docs.microsoft.com/en-us/learn/modules/introduction-power-automate/)
  - [Learn how to create your own flows on Microsoft Learn](https://docs.microsoft.com/en-us/learn/modules/get-started-flows/)
- PowerApps: 
  - [Documentation](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/getting-started)
  - [Short introduction on Microsoft Learn](https://docs.microsoft.com/en-us/learn/modules/introduction-power-apps/)
  - [Learn how to create your own apps on Microsoft Learn](https://docs.microsoft.com/en-us/learn/modules/get-started-with-powerapps/)


