# Part 1: Getting Started with Edge Impulse
## Who is this for?
- Students curious about Machine Learning as a career path.
- Professionals who want to expand their career prospects.
- Hobbyist who enjoy learning various Machine Learning tools.
## Learning Outcome
- An introduction to what is and how does a machine learning pipeline work.
- What is and how to used Edge Impulse to train and deploy ML models.
## Time Estimate
- 45-60 minutes
## Pre-requisites
1. Fully charged phone
2. Laptop with internet connection

## Additional Resources
1. [Google slideshow for presentations](https://docs.google.com/presentation/d/1UIVBuwPvIvu1EBK7R0EDb1Z5nWFuEPHmMjgGr-FKbtE/edit?usp=sharing)

   
## Start Here
#### Step 1: ON YOUR LAPTOP navigate to https://www.edgeimpulse.com/ and click "Get Started"
![alt text](/Part-1/Part-1-Images/step1.png)

#### Step 2.1: Create a free account using either Google, Github or regular email sign-up. ![alt text](/Part-1/Part-1-Images/step2.png)

#### Step 2.2: You will be prompted through a few screens asking for username and your role. Fill those out and you are good to go.

#### Step 3: Once you are finished creating your account you will see the screen below. Here make sure to choose "Image classification" and then click "Image classification".
![alt text](/Part-1/Part-1-Images/step3.png)

#### Step 4: We will follow this tutorial to introduce ourselves to the Edge Impulse tool. On this step you are going to decide what 2 classes your classification model will be detecting on top of the unknown class. My two classes are going to be Cobalt and Renzo.
![alt text](/Part-1/Part-1-Images/step4.png)

#### Step 5: Scan the QR Code using your phone by opening your camera app and aiming your phone at the QR code. This will connect your phone to the Edge Impulse project for the purpose of collecting data. ![alt text](/Part-1/Part-1-Images/step5.png)


#### Step 6: After the previous your phone is connected to the project. On your phone you will be prompted to give access to the camera, AGREE TO GIVE IT. 
#### IMPORTANT NOTE: if you dont give access within a minute you will receive an "Image collection failed" error and will have to restart the process from STEP 5.  

#### STEP 7: On this step you are prompted to provide 30 images of the first class. Make sure to follow these guidelines:
1. **Different angles:** capture front, sides, top and bottom views.
2. **Ensure good lighting:** avoid shadows and reflections.
3. **Vary distance:** include close-ups and long distance pictures.
4. **Keep background clear:** ensure your background is simple and free of extra objects. This helps the model focus on your object.

![alt text](/Part-1/Part-1-Images/step7_1.png)

#### Once you collected 30 images of the first class it will look something like this. ![alt text](/Part-1/Part-1-Images/step7_2.png)

#### Steps 8 & 9: This pretty much going to be like the previous step but we are collecting 30 pictures both of the 2nd and unknown classes. Click on either of the 'collect images' boxes and start taking pictures for that respective class.

#### After all the pictures have been collected it should look like this:![alt text](/Part-1/Part-1-Images/step9.png) 

#### Proceed by clicking "...create an impulse". 

#### Step 10: You will see this screen! Here it shows you the stages of an 'Impulse'. You could see how the data you collected goes through a pre-processing step then into a neural network that learns the parameters of each of the classes and is ready to do some predicting.
#### Proceed by clicking: "Got it, let's move on to DSP" ![alt text](/Part-1/Part-1-Images/step10.png)

#### Step 11: This screen explains how DSP is applied in pre-processing your images data and why it is helpful. Proceed by clicking the "Got it, let's generate features"

#### Step 12: This screen shows the step where Edge Impulse automatically extracts features from the data you provided. You could think of "Features" as parameters that each data sample has and that each class has its own grouping of features and that's how the model learns to differentiate each class.

#### Before we move on notice how the features of the data I collected are not split into clear groupings by class. How do you think that will affect the model trained on this data? Discuss this with someone next to you. 
![alt text](/Part-1/Part-1-Images/step12.png)

#### Step 13: On this step you will see the step where Edge Impulse trains the model on the previously extracted features. At the top left you can see the all the training settings you can change.
#### After the initial training is finished you can minimize the window on the bottom right and play around with the training setting and explore how they affect model's performance. 
Notes:
1. (Spend 10-15 minutes to let the attendees play around with it)
![alt text](/Part-1/Part-1-Images/step13.png)

#### Once the model finished training you will see a tab with model's performance. The metrics we care about right now are: Accuracy and Loss.
1. **Accuracy** is how correct the model is predicting overall in the validation set. The higher the better.
2. **Loss** is a summation of the erros made for each sample in the validation set. The lower the better.
![alt text](/Part-1/Part-1-Images/step13_performance.png)

#### Step 14: After clicking "Next, take your impulse for a spin" you will see this pop up. Proceed to scan it with your phone and see how your model performs on real world data!!!![alt text](/Part-1/Part-1-Images/step14.png)

#### Step 15: After clicking "View summary to finish tutorial" you will see a congratulations window which will also show a quick review of your model's performance, but who cares about? You are now an Embedded Machine Learning Engineer!!! ![alt text](/Part-1/Part-1-Images/step15.png)

# Troubleshooting
#### What if images fails to upload part way through?

#### What if my phone disconnects or timeouts while on the collecting pictures stage?

#### What to do if I clicked quit tutorial at any step of this process? 
