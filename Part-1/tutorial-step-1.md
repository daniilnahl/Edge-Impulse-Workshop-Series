# Part 1: Getting Started with Edge Impulse
## IMPORTANT PRE-REQUISITES
1. FULLY CHARGED PHONE
2. LAPTOP WITH INTERNET CONNECTION

#### Step 1: ON YOUR LAPTOP navigate to https://www.edgeimpulse.com/ and click "Get Started"
![alt text](/Edge-Impulse-Workshop-Series/Part-1/step1_1.png)

#### Step 2.1: Create a free account using either of the provided options. ![alt text](/Edge-Impulse-Workshop-Series/Part-1/step2_2.png)

#### Step 2.2: You will be prompted through a few screens asking for username and your role. Fill those out and you are good to go.

#### Step 3: Once you are finished creating your account you will see the screen below. Here make sure to choose "Image classification" and then click "Image classification".
![alt text](/Edge-Impulse-Workshop-Series/Part-1/step3_3.png)

#### Step 4: We will follow this tutorial to introduce ourselves to the Edge Impulse tool. On this step you are going to decide what 2 classes your classification model will be detecting. My two classes are going to be Cobalt and Renzo.
![alt text](/Edge-Impulse-Workshop-Series/Part-1/part1_step4.png)

#### Step 5: Scan the QR Code using your phone which will connect it to this Edge Impulse project. ![alt text](/Edge-Impulse-Workshop-Series/Part-1/part1_step5.png)


#### Step 6: After the previous your phone is connected to the project. On your phone you will be prompted to give access to the camera, AGREE TO GIVE IT. 
#### IMPORTANT NOTE: if you dont give access within a minute you will receive an "Image collection failed" error and will have to restart the process from STEP 5.  

#### STEP 7: On this step you are prompted to provide 30 images of the first class. Make sure you take pictures of this class from different angles, so the model will be able to detect this class from various perspectives.
![alt text](/Edge-Impulse-Workshop-Series/Part-1/2026-04-17_19-52.png)

#### Once you collected 30 images of the first class it will look something like this. ![alt text](/Edge-Impulse-Workshop-Series/Part-1/step7_2.png)

#### Step 8 & 9: This pretty much going to be like the previous step but we are collecting pictures for the 2nd and unknown classes. Click on either of the 'collect images' boxes and start taking pictures for that respective class.

#### After all the pictures have been collected it should look like this:![alt text](/Edge-Impulse-Workshop-Series/Part-1/step9_1.png) 

#### Proceed by clicking "...create an impulse". 

#### Step 10: You will see this screen! Here it shows you the stages of an 'Impulse'. You could see how the data you collected goes through a pre-processing step then into a neural network that learns the parameters of each of the classes and is ready to do some predicting.
#### Proceed by clicking: "Got it, let's move on to DSP" ![alt text](/Edge-Impulse-Workshop-Series/Part-1/step10.png)

#### Step 11: This screen explains how DSP is applied in pre-processing your images data and why it is helpful. Proceed by clicking the "Got it, let's generate features"

#### Step 12: This screen shows the step where Edge Impulse automatically extracts features from the data you provided. You could think of "Features" as parameters that each data sample has and that each class has its own grouping of features and that's how the model learns to differentiate each class.

#### Before we move on notice how the features of the data I collected are not split into clear groupings by class. How do you think that will affect the model trained on this data? Discuss this with someone next to you. 
![alt text](/Edge-Impulse-Workshop-Series/Part-1/step%2012.png)

#### Step 13: On this step you will see the step where Edge Impulse trains the model on the previously extracted features. At the top left you can see the all the training settings you can change, we will explore how those setting affect the model in part 3 of this workshop series.  ![alt text](/Edge-Impulse-Workshop-Series/Part-1/step13.png)
# Troubleshooting
add known errors and mistakes here after testing this on someone.

*1. what happens if they click quit tutorial at any step?*
*2. *