# Create PowerApp

## Prerequisites
- Part 1 has to be completed to make this PowerApp functional. 

## Create simple form app with integrated model from AML in PowerApps

1. Go to [www.powerapps.microsoft.com](http://powerapps.microsoft.com/) and sign in, using the same account with which you created the flow in Part 1.
2. Create a new **Canvas app from blank**. 
3. Give your new app a name and choose the phone layout. You should see something like this:

<img src="/media/Picture6.png" alt="drawing" width="600"/>

We need two things to make this app work. 
- The ability to input data that will be sent to our endpoint. We will use **Text Inputs** for this. Our model expects eight values so we need eight inputs.
- A button to initialize the flow we created in part 1. We will use a **Button** for this.

4. Under **Insert**, find **Text** and add a **Text input** to your app. Repeat this eight times and put them below each other. 
5. To make it a bit more user friendly, add labels so we know what input we are putting in. Under **Insert**, find **Label** and add this to your app. Again, repeat this eight times and put each label on the same row as a text input.
You should end up with something like this:

<img src="/media/Picture7.png" alt="drawing" width="600"/>

> Protip: You can change the name and the default value of the **Text Input** to make it easier to work with. See the red arrows in the screenshot above where you can change these two things.

6. Now, we need to add our button to kick off our flow. Under **Insert**, find **Button** and add this to the bottom of your app. You can change the text that appears on the button to e.g. "Analyze" in the **Properties** on the right of your screen. 
7. Make sure you have selected the button, then under **Action**, select **PowerAutomate**. A pop-up will appear. Your previously created flow should show up here as one of the options. Select your flow so that it will be attached to the button.
8. Complete the flow's parameters in the formula bar above. If you've renamed your text inputs, you can use the following formula:
`Set(Prediction,DemoDiabetesACI.Run(Value(Pregnancies.Text),Value(PlasmaGlucose.Text),Value(DiastolicBloodPressure.Text),Value(TricepsThickness.Text),Value(SerumInsulin.Text),Value(BMI.Text),Value(DiabetesPedigree.Text),Value(Age.Text))`
    - Set(Prediction, ...: this makes sure the result of your flow is saved as a collection name Prediction so that we can visualize it later in our app
    - DemoDiabetesACI: name of your flow
    - Pregnancies, PlasmaGlucose, etc: name of your Text Inputs as they appear on the left in your Tree View. 
  
    <img src="/media/Picture8.png" alt="drawing" width="600"/>
  
9. Finally, we want to visualize our result in the same app. Under **Insert**, find **Label** and add it below your button.
10. Select the newly inserted label, make sure you're changing the **Text** property and change it to have the value of our newly created collection **Prediction** (this is what we created with **Set** in the formula for our button):
`Prediction.predictions`

<img src="/media/Picture9.PNG" alt="drawing" width="600"/>


