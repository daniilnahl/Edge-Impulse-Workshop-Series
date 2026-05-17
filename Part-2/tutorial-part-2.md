# Part 2: Setting up Data Collection on Nano33
## Learning Outcome
- placeholder 1
- placeholder 2
- placeholder 3

# Time Estimate
- TBD

# Pre-requisites 
**(physical)** 
1. Fully charged laptop with Windows 10/11
2. Arduino Nano 33 BLE
3. Micro-USB cable 

**(software)**
1. Installed "Build Tools for Visual Studio 2022" with "Desktop development with C++". Go to [this link](https://my.visualstudio.com/Downloads?q=Visual%20Studio%202022) and download the below selection:
![alt text](/Part-2/Part-2-Images/vs2022-c++.jpg)
2. Installed "npm 1.2.2" via [nvm-setup.exe 1.2.2](https://github.com/coreybutler/nvm-windows/releases). Note during installation wizard un-check these options:
![alt text](/Part-2/Part-2-Images/nvm-pre-workshop.png)

# Start Here
### Step 1 
Navigate to Edge Impulse dashboard via the [following link](https://studio.edgeimpulse.com/studio/965987). Then click on your profile picture icon. It will look like this:
![alt text](/Part-2/Part-2-Images/part2-step1.png)
## Step 2
Proceed to click on "Create new project":
![alt text](/Part-2/Part-2-Images/part2-step2_1.png)

Afterwards you will see this screen. You can give your project any name you like and other options are up to your discretion as what you chose don't really matter for our purposes. 

![alt text](/Part-2/Part-2-Images/part2-step2_2.png)
## Step 3
After you create your project you will be navigated to the screen below. Notice that at the top middle of your screen is your project name. **Click on the option where it says, "Collect new data":**
![alt text](/Part-2/Part-2-Images/part2-step3.png)
## Step 4
You will be navigated to a new screen and a pop-up called "Collect new data" will be shown with 3 options.
We are interested in THIRD options which says, "Connect your device or development board":
![alt text](/Part-2/Part-2-Images/part2-step4.png)
## Step 5
You will see a new screen with two options: 
1. connecting a device via data forwarded 
2. connecting a supported device.

![alt text](/Part-2/Part-2-Images/part2-step5_1.png)

**Click on the option to connect a supported device** and type-in 'Arduino Nano 33 BLE' and select it:
![alt text](/Part-2/Part-2-Images/part2-step5_2.png)
![alt text](/Part-2/Part-2-Images/part2-step5_3.png)


## Step 6
After selecting 'Arduino Nano 33 BLE' we are going setup a connection between the Arduino microcontroller and Edge Impulse. To achieve this we will need to install:
- [Edge Impulse CLI](https://docs.edgeimpulse.com/tools/clis/edge-impulse-cli/installation)
- [Arduino CLI](https://arduino.github.io/arduino-cli/1.4/installation/)

**Make you sure you are on a machine with Windows 10/11 as this tutorial is specifically made for Windows!**

## Step 7: Installing Edge Impulse CLI
We are going to begin by installing [Edge Impulse CLI](https://docs.edgeimpulse.com/tools/clis/edge-impulse-cli/installation). Click the hyperlink and you will be navigated to this screen where you can follow the official steps. I am going to replicate them in here with more details, I recommend you follow my steps.

**Use Command Prompt (CMD) for the installations unless stated otherwise!**

---

**Before we can download Edge Impulse CLI, we must download these pre-requisites:**
### Python 3 on your computer (if you haven't already). This hyperlink will navigate you to [Python Releases for Windows](https://www.python.org/downloads/windows/). 

In this tutorial we will be installing "Python install manager" instead of the standalone python install due to simplicity sake. 
![alt text](/Part-2/Part-2-Images/step7_python_1.png)
![alt text](/Part-2/Part-2-Images/step7_python_2.png)
After downloading the installer proceed to follow its installation steps. 

Once that is complete you can test if you have successfully installed python by navigating to "Command Prompt" and typing "python --version". If everything was installed correctly you should see you python's version in the terminal like "Python 3.XX.X".

### To install Node.js 20 you must have installed the 'nvm' from 'Pre-requisites', if you haven't ensure you do before beginning this step. Follow the below instructions:
1. Open **Command Prompt as an Administrator** and type in (to install correct version of node.js):
```
nvm install 20
```
2. To ensure you are using this version of node.js type in:
```
nvm use 20.20.2
```

To check if Node.js was installed properly open "Command Prompt" and type in:
1. "node -v" and you should see "v20.20.2".

**NOTE YOU MUST INSTALL THIS EXACT VERSION OF NODE.js or THE EDGE IMPULSE INSTALLATION WILL FAIL!!!**

### Now we can install the Edge Impulse CLI! Open **Command Prompt** and type in:
```
npm install -g edge-impulse-cli --force
```
If you encounter any errors during this step ensure you have the correct "Pre-requisities" versions installed!!!

## Step 8: Installing Arduino CLI
We can just follow this [1-minute Youtube tutorial](https://www.youtube.com/watch?v=1jMWsFER-Bc) 

IF you rather follow written instructions, they are attached below:

1. Navigate to [Arduino CLI installation page](https://arduino.github.io/arduino-cli/1.4/installation/)
2. Scroll down untill you hit 'Latest release' section and ensure you install 'Windows exe 64 bit'
![alt text](/Part-2/Part-2-Images/step8-arduino_1.png)
3. Extract the zip folder into your 'Downloads'
![alt text](/Part-2/Part-2-Images/step8-arduino_2.jpg)
4. Copy the address of the extract folder.
 ![alt text](/Part-2/Part-2-Images/step8-arduino_3.jpg)
5. Open "Edit the system environment variables->Environment Variables"
6. Select "Path->Edit..."
7. Click "new" and paste the copied address.
8. To finish the process exiting everything by clicking "Ok".
9. Check for correct installation via opening "Command Prompt" and typing:
```
arduino-cli
```

# Troubleshooting

