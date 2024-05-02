# Satyansh Worklog

This worklog contains the progress of a PCB design project aimed at developing a medical device that records audio and transmits it via Bluetooth to a smartphone application. Below are key milestones and updates:

# 2024-02-05 - Initial Brainstorming and Approval

The project kicked off with an initial brainstorming session where the concept of a medical device capable of recording and transmitting audio was discussed and approved. Objectives were set, and preliminary designs were drafted. We set the requirements and each person claimed what they wanted to work on and planned out the required technology. I focused on the Software Side so i decided to develop natively on IOS using swift to build the phone application and to write the microphone and bluetooth programs. I decided to host all backend resources on AWS cloud.

# 2024-02-10 - App update

After doing research on application development, I found a framework called React-Native which I found would speed up intial development of the app design and bluetooth functionalities.
[link](https://reactnative.dev/docs/environment-setup)

# 2024-02-20 - DEvelopment board setup with microphone and bluetooth communication

Set up a XIAO board to test the microphone input and Bluetooth output. This included configuring the Bluetooth module for optimal transmission and testing microphone sensitivity. Had to trouble shoot a lot with setting up the file system on the XIAO board to save audio.
![](XIAO_board.png)

# 2024-02-28 - Developed Mobile application to test bluetooth

Developed and tested a mobile application prototype designed to connect with the Bluetooth module. This app was essential for real-time audio data reception and helped in assessing the quality and stability of the Bluetooth connection. I used the following package to set up bluetooth
[link](https://github.com/dotintent/react-native-ble-plx)

# 2024-04-10 - Received and Programmed pcb

Received the printed circuit boards (PCBs) from the manufacturer. Programmed the PCBs with the initial firmware, ensuring all components such as the Bluetooth module and microphone were functioning as expected. The microphone however was not programmed. Since the pcb was not programmed as an esp32 board, we i had to research a different library to use with the bluetooth and microphone.
![](pcb.png)
[link](https://docs.arduino.cc/hardware/nano-33-ble/)

# 2024-04-12 - Updates programs to be compatible with pcb filesystem and different bluetooth module

Updated the device's firmware to address compatibility issues with the new PCB filesystem and a different Bluetooth module than initially tested. This included modifying the code to accommodate hardware-specific requirements and optimizing performance.

# 2024-04-14 - Set up AWS Cloud

Set up storage for the audio files being transmitted to the app as well as a lambda function that processsed our audio files through the trained network to make predictions.
These were the main resouces we used to set up the cloud to work with the application.
[link]https://docs.aws.amazon.com/lambda/latest/dg/images-create.html
[link](https://jaka-tertinek.medium.com/upload-files-from-react-native-app-to-aws-s3-3d3cb85e9d4)
