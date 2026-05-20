# Part 3: Training a Model and Deploying it on Nano33
## Learning Outcome
1. Train and optimize a neural network classifier using Edge Impulse based on data you collected and prepared for Machine Learning. 

2. Deploy a Machine Learning model to Arduino Nano33 by exporting the model library, integrating it within the Arduino IDE, and executing real-time inferencing to trigger hardware responses.

# Time Estimate
- 60 minutes

# Pre-requisites 
**(physical)** 
1. Fully charged laptop with Windows 10/11
2. Arduino Nano 33 BLE
3. Micro-USB cable 
4. Project and Data from Part 2.

# Start Here
## Step 1: Managing Data
During the previous part of this workshop we collected data for 3 data classes. Now we need to prepare the data for training and testing. 
1. Navigate back to "Dashboard" and scroll down until you find "Danger zone". There click on "Perform train / test split" which will automatically split the data we collected into training and testing.
![alt text](/Part-3/Part-3-Images/step1-1.png)
2. Then navigate back to "Data Acquisition" and it should look like this:
![alt text](/Part-3/Part-3-Images/step1-2.png)

IF you are getting a warning about the data split click on the small chart icon next to "Train / Test Split" which will show the percentage of each classes' split. 
![alt text](/Part-3/Part-3-Images/step1-3.png)
![alt text](/Part-3/Part-3-Images/step1-4.png)


For classes in the red manually move a data sample from that specific class into the test split. You can do that by clicking 3 dots symbol next to a data sample and selecting "Move to test set".
![alt text](/Part-3/Part-3-Images/step1-5.png)

## Step 2: Creating an Impulse
1. Navigate to "Experiments" and select "Create new impulse":
![alt text](/Part-3/Part-3-Images/step2-1.png)

2. It will open this menu where we will need to choose:
    - Processing block: prepares your data for a machine learning algorithm
    - Learning block: the machine learning algorithm that creates the model 

![alt text](/Part-3/Part-3-Images/step2-2.png)   
    
3. For "Processing block" choose "Spectral Analysis":
![alt text](/Part-3/Part-3-Images/step2-3.png)

4. For "Learning block" you MUST choose "Classification":
![alt text](/Part-3/Part-3-Images/step2-4.png)

5. After the selection it should look like this. Ensure to click on the check-box for "Spectral features" or you will get an error:
![alt text](/Part-3/Part-3-Images/step2-5.png)
 
## Step 3: Features Analysis
1. Navigate to "Spectral features" under "Impulse design".

Then proceed to:
1. Click "Autotune parameters"
2. Then click "Save parameters"

Which will analyze your entire dataset and find the most optimal parameter configuration for the "Processing block" we chose. 
![alt text](/Part-3/Part-3-Images/step3-1.png)


2. After clicking "Save parameters" it will take us to "Generate features" page. On this step the features from our data samples will be extracted which then will be used to train our model. 

    - Here you can select "Calculate feature importance" which will analyze the significance of each feature in determining a data class.
    - You can also choose to normalize features which could improve the model performance. 
    
    
**Proceed to press "Generate features" once you are ready**
    
![alt text](/Part-3/Part-3-Images/step3-2.png)
    
    
**After it has finished your screen should look something like this**

![alt text](/Part-3/Part-3-Images/step3-3.png)

## Step 4: Training the Model!
After we have extracted features we are now ready to train the model! 
1. Navigate to "Classifier" under "Impulse design". On this page you can configure the neural network. You can go ahead and change parameters as you like to see how it affects model's performance while I will be leaving be mine as it is. **Click Save & train to create the model**.

![alt text](/Part-3/Part-3-Images/step4-1.png)

2. After the model training is finished you can go back and modify network and training settings to try and improve it. Here's how it should look like:

![alt text](/Part-3/Part-3-Images/step4-2.png)

## Step 5: Testing the Model
You have 2 options to test your model:
1. Live classification: where it connects back Nano33 and classifies in real time.
2. Model testing: where it tests your model on test set samples. 

For this workshop we will be doing **Model testing** for the sake of time, but you are free to try out live classification on your own at a later time. 

---

1. Proceed to "Model testing" under "Impulse design" then clock on "Classify all" to see how your model performs on test data.
![alt text](/Part-3/Part-3-Images/step5-1.png)
2. On the right side you will see it's performance. Depending on how many unique samples you had the performance might be better than if you had a few long samples. 
![alt text](/Part-3/Part-3-Images/step5-2.png)

## Step 6: Deploying the Model to Nano33
Now the moment has come. We collected data, we trained the model, we tuned for the best performance and now we are here. Time to deploy this model onto Nano33.

1. Navigate to "Deployment" under "Impulse design" where you will find the Deployment Configuration Menu. 
![alt text](/Part-3/Part-3-Images/step6-1.png)

2. Click on "Deployment Target" and find "Arduino Library" and proceed to click build. This will create an Arduino library that contains code we will modify to blink specific colors based on the data class detected:
![alt text](/Part-3/Part-3-Images/step6-2.png)


3. Afterwards it is done building you will see this screen which says exactly what will be doing:
![alt text](/Part-3/Part-3-Images/step6-3.png)


4. Open Arduino IDE on your laptop -> click Sketch -> Include Library -> Add .ZIP Library (and choose the .zip folder we created) 
![alt text](/Part-3/Part-3-Images/step6-4.jpg)

5. Then we need to add 1 more library: click Sketch -> Include Library -> Manage Libraries...
![alt text](/Part-3/Part-3-Images/step6-5.jpg)


In the search bar look-up "Arduino_LSM9DS1" and click "INSTALL":
![alt text](/Part-3/Part-3-Images/step6-6.jpg)

6. After library is processed, create a new sketch and copy and paste the below code in:

**Make sure to change the library name to whatever you named your library!!!**


```
/* Edge Impulse ingestion SDK
 * Copyright (c) 2022 EdgeImpulse Inc.
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 *
 */

/* Includes ---------------------------------------------------------------- */
#include <EdgeImpulse-Workshop-Project_inferencing.h> <---------- CHANGE THIS. REPLACE IT WITH <[YOUR LIBRARY NAME].h> 
#include <Arduino_LSM9DS1.h> //Click here to get the library: https://www.arduino.cc/reference/en/libraries/arduino_lsm9ds1/

/* Constant defines -------------------------------------------------------- */
#define CONVERT_G_TO_MS2    9.80665f
/**
 * When data is collected by the Edge Impulse Arduino Nano 33 BLE Sense
 * firmware, it is limited to a 2G range. If the model was created with a
 * different sample range, modify this constant to match the input values.
 * See https://github.com/edgeimpulse/firmware-arduino-nano-33-ble-sense/blob/master/src/sensors/ei_lsm9ds1.cpp
 * for more information.
 */
#define MAX_ACCEPTED_RANGE  2.0f

/*
 ** NOTE: If you run into TFLite arena allocation issue.
 **
 ** This may be due to may dynamic memory fragmentation.
 ** Try defining "-DEI_CLASSIFIER_ALLOCATION_STATIC" in boards.local.txt (create
 ** if it doesn't exist) and copy this file to
 ** `<ARDUINO_CORE_INSTALL_PATH>/arduino/hardware/<mbed_core>/<core_version>/`.
 **
 ** See
 ** (https://support.arduino.cc/hc/en-us/articles/360012076960-Where-are-the-installed-cores-located-)
 ** to find where Arduino installs cores on your machine.
 **
 ** If the problem persists then there's not enough memory for this model and application.
 */

/* Private variables ------------------------------------------------------- */
static bool debug_nn = false; // Set this to true to see e.g. features generated from the raw signal

/**
* @brief      Arduino setup function
*/
void setup()
{
    pinMode(LEDR, OUTPUT);
    pinMode(LEDG, OUTPUT);
    pinMode(LEDB, OUTPUT);
    digitalWrite(LEDR,HIGH);
    digitalWrite(LEDG,HIGH);
    digitalWrite(LEDB,HIGH);

  
      
    // put your setup code here, to run once:
    Serial.begin(115200);
    // comment out the below line to cancel the wait for USB connection (needed for native USB)
    while (!Serial);
    Serial.println("Edge Impulse Inferencing Demo");

    if (!IMU.begin()) {
        ei_printf("Failed to initialize IMU!\r\n");
    }
    else {
        ei_printf("IMU initialized\r\n");
    }

    if (EI_CLASSIFIER_RAW_SAMPLES_PER_FRAME != 3) {
        ei_printf("ERR: EI_CLASSIFIER_RAW_SAMPLES_PER_FRAME should be equal to 3 (the 3 sensor axes)\n");
        return;
    }
}

/**
 * @brief Return the sign of the number
 * 
 * @param number 
 * @return int 1 if positive (or 0) -1 if negative
 */
float ei_get_sign(float number) {
    return (number >= 0.0) ? 1.0 : -1.0;
}

/**
* @brief      Get data and run inferencing
*
* @param[in]  debug  Get debug info if true
*/
void loop()
{
    ei_printf("\nStarting inferencing in 2 seconds...\n");

    delay(2000);

    ei_printf("Sampling...\n");

    // Allocate a buffer here for the values we'll read from the IMU
    float buffer[EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE] = { 0 };

    for (size_t ix = 0; ix < EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE; ix += 3) {
        // Determine the next tick (and then sleep later)
        uint64_t next_tick = micros() + (EI_CLASSIFIER_INTERVAL_MS * 1000);

        IMU.readAcceleration(buffer[ix], buffer[ix + 1], buffer[ix + 2]);

        for (int i = 0; i < 3; i++) {
            if (fabs(buffer[ix + i]) > MAX_ACCEPTED_RANGE) {
                buffer[ix + i] = ei_get_sign(buffer[ix + i]) * MAX_ACCEPTED_RANGE;
            }
        }

        buffer[ix + 0] *= CONVERT_G_TO_MS2;
        buffer[ix + 1] *= CONVERT_G_TO_MS2;
        buffer[ix + 2] *= CONVERT_G_TO_MS2;

        delayMicroseconds(next_tick - micros());
    }

    // Turn the raw buffer in a signal which we can the classify
    signal_t signal;
    int err = numpy::signal_from_buffer(buffer, EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE, &signal);
    if (err != 0) {
        ei_printf("Failed to create signal from buffer (%d)\n", err);
        return;
    }

    // Run the classifier
    ei_impulse_result_t result = { 0 };

    err = run_classifier(&signal, &result, debug_nn);
    if (err != EI_IMPULSE_OK) {
        ei_printf("ERR: Failed to run classifier (%d)\n", err);
        return;
    }

    // print the predictions
ei_printf("Predictions ");
    ei_printf("(DSP: %d ms., Classification: %d ms., Anomaly: %d ms.)",
        result.timing.dsp, result.timing.classification, result.timing.anomaly);
    ei_printf(": \n");
    for (size_t ix = 0; ix < EI_CLASSIFIER_LABEL_COUNT; ix++) {
      auto res = result.classification[ix].value;
        ei_printf("    %s: %.5f\n", result.classification[ix].label, res);
      if (ix == 0 && res > 0.8){
        digitalWrite(LEDR, LOW);
        digitalWrite(LEDG, LOW);
        digitalWrite(LEDB, HIGH);
      }
      if (ix == 1 && res > 0.6){
        digitalWrite(LEDR, HIGH);
        digitalWrite(LEDG, LOW);
        digitalWrite(LEDB, LOW);
      }
    if (ix == 2 && res > 0.8){
        digitalWrite(LEDR, LOW);
        digitalWrite(LEDG, HIGH);
        digitalWrite(LEDB, LOW);
      }
    }
#if EI_CLASSIFIER_HAS_ANOMALY == 1
#endif
}


#if !defined(EI_CLASSIFIER_SENSOR) || EI_CLASSIFIER_SENSOR != EI_CLASSIFIER_SENSOR_ACCELEROMETER
//#error "Invalid model for current sensor"
#endif
```

7. Click the "arrow to the left" symbol up top which will start uploading code to Nano33. It will take a few minutes to upload it. 


## Step 7: Live Test the Model!
Congrats, you have successfully deployed a Machine Learning model onto a microcontroller!  
