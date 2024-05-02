# Aryan Worklog

This worklog contains the progress of a PCB design project aimed at developing a medical device that records audio and transmits it via Bluetooth to a smartphone application. Below are key milestones and updates:

# 2024-01-29 - Meeting with Richard and Eric from Carle College of Medicine

We met with Richard and Eric to discuss the intricacies of their pitched project and clear up any of our doubts regarding the vision for the solution. Afterward, we created and submitted our RFA to the web board.

# 2024-02-01 - Research and Initial Timeline

We created a rough timeline for the remainder of the semester to have an idea of how we would go about finishing this project. We spent some time researching what components we definitely would need for our PCB.

# 2024-02-05 - Initial Brainstorming and Approval

The project kicked off with an initial brainstorming session where the concept of a medical device capable of recording and transmitting audio was discussed and approved. Objectives were set, and preliminary designs were drafted. We set the requirements and each person claimed what they wanted to work on and planned out the required technology. I focused primarily on the sensing and power subsystems of the PCB. I also had to focus on getting the team enough data so our CNN would have enough training samples to help increase the accuracy and reliability of the CNN as shown through the Precision, Recall, and F1-score. 

# 2024-02-07 - Project Proposal

We received feedback from Richard and our TA Surya related to what we would need in our block diagram and what our high-level requirements would be.
Finally, we began working on our project proposal which is due on 02/08.

<img width="377" alt="Screen Shot 2024-05-02 at 12 05 28 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/d7e61bed-a97f-4262-b07d-75bc0079d82d">

Figure 1: Arteriovenous Fistula Monitoring Device General Design

# 2024-02-12 - Beginning Design of PCB

After doing more research on PCB development, we began with making a components list of what we would need. I also started to look into the PCB packaging/3d model that our PCB would rest in. We needed this 3d model because the patient wearing the AVF would have to wear it throughout the day and we don't want the electrical components coming in contact with the skin. I also had to make sure that the 3d model would be flat so there is more surface area for the adhesive. We also divided up the subsystems so I was in charge of the sensing and power subsystems, Rishab worked heavily on the control subsystem and CNN, and Satyansh worked on the app subsystem. 

# 2024-02-19 - Research for Sensing Subsystem

I had to figure out which microphone would fit our requirements and scope of our project. I did a lot of research before I came across the MEMS (Micro-Electro-Mechanical Systems) microphones which are well-suited for various medical applications, offering several advantages:

1. MEMS microphones are very small, making them ideal for integration into compact medical devices, including wearable technology and implantable devices.
2. These microphones require less power, which is beneficial for us since our device needs to operate continuously for long periods since it is a wearable health monitoring device.
3. MEMS microphones can also provide high-quality audio capture, which is so crucial for applications like digital stethoscopes used to monitor heart sounds. Their reliability and consistency in performance is so critical for us.
4. Not as important, but MEMS microphones are also very cost-effective.
   
<img width="874" alt="Screen Shot 2024-05-02 at 12 21 29 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/12551669-f6eb-4a4b-801a-c9acf9d1f8dd">

# 2024-02-23 - Finishing PCB Design for Sensing Subsystem

<img width="165" alt="Screen Shot 2024-05-02 at 12 27 11 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/0216ce3e-c688-425b-8c92-faf9a4eb7999">

To justify the selection of this microphone, consider a signal-to-noise ratio (SNR) equation:

SNR  = 20log10 (Signal Amplitude / Noise Amplitude)

Assuming the microphone effectively captures signals (fistula sounds) at an amplitude of 30 db and the background noise is at an amplitude of 20 db the SNR can be calculated. For our application, a higher SNR is critical as it indicates that the fistula sounds are much clearer relative to the background noise, allowing for more accurate monitoring and analysis.
Using the given signal amplitude of 30 dB for the fistula sounds and a background noise amplitude of 20 dB, the signal-to-noise ratio (SNR) calculation yields an SNR of approximately 3.52 dB. The SPH0641LU4H-1's performance characteristics, including its high sensitivity and ability to capture low-frequency sounds accurately, contribute to achieving a much higher SNR. This ensures that the device can reliably detect and analyze the sounds of blood flow through the fistula, making it a justified choice for our monitoring application.

# 2024-02-29 - Power Subsystem

To accommodate the microcontroller and other components requiring regulated 3.3V power, a voltage regulator (model TPS79333-EP) steps down the 5V from the battery to a stable 3.3V output. This regulator was selected for its low dropout voltage and overall efficiency.

The regulated 3.3V output from the TPS79333-EP is distributed to the NINA-B306-00B-00 microcontroller and other critical subsystems, such as the sensing and control units.
Power Management: This system minimizes energy waste and maximizes battery life by providing each component with the precise voltage it requires for optimal operation. Through this method, we ensure that the device remains energy-efficient, extending the operational duration between charges while maintaining high performance and reliability.

<img width="505" alt="Screen Shot 2024-05-02 at 12 34 24 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/af76e3fd-656c-4939-9f5a-7497f05bf055">

# 2024-03-07 - 3d model research and initial design

At this point, I started to divert my focus to the 3d enclosure for our design. I needed to build a structure would allow for concealed electrical components while being like other medical devices that can be applied directly to the patient’s skin.  Additionally, it would serve as a surface that would allow for a sleek design that would not be too burdensome on the patient and have a port that will have an LED that will demonstrate the fistula status.  Additionally, the patient will have the option to place a strap on the device if they wish, and the shape of the superior portion of the device allows for easy strap placement. 

# 2024-03-25 - Final 3d model 

I finished the 3d model over the last two weeks and got it printed. I used a rubber that was recommended by Richard and Eric.

<img width="244" alt="Screen Shot 2024-05-02 at 12 39 34 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/2944618e-3de4-4871-8f32-79132676865b">

The microphone module is placed towards the rear of the device, where the case has an almost conical head which would ideally allow for reverberations from the fistula to amplify the sound for the microphone.  Additionally, the USB-C port is present which would allow for wired data collection from the electrical components.  The wired connection capability can be utilized for data capture, or the data can be collected through the app via a wireless data transfer (Bluetooth).  Figure 3 demonstrates a USB-C connection with a laptop, which allows for data transfer during device testing.  

<img width="244" alt="Screen Shot 2024-05-02 at 12 39 51 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/193c2ec4-77dd-4363-b05c-7c5936cb12d3">

Bottom view of the device.  The bottom of the device is designed to stick to an adhesive, and the highlighted area is designed to channel a resonant signal from the skin to the omnidirectional microphone module.

<img width="296" alt="Screen Shot 2024-05-02 at 12 40 05 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/92366abb-7538-4e9c-a516-798027944461">

# 2024-04-03 - Collect samples for machine learning algorithm (CNN)

Data Collection, Cleaning, and Simulation
A significant portion of our advancements in the software component is attributed to data collection, cleaning, and simulation efforts. We used a specialized fistula pump to mimic a broad spectrum of AVF flow patterns to create a dataset mirroring real-world conditions. After the design review, we made sure that this dataset has a lot of different heartbeats and we also introduced white noise so we can account for white noise that people will have in real life as well as to expand the samples. 

After the design review, we also recognized the limitations of just physically collected data, so we are also going to include additional simulated data to our datasets. This simulation will replicate a wide range of venous hum patterns, encompassing both continuous and pulsatile flows. This larger dataset bolsters the training of our machine learning models, significantly enhancing their predictive accuracy and reliability. Through rigorous data cleaning, we ensure the integrity and utility of this information for our model training processes.

<img width="512" alt="Screen Shot 2024-05-02 at 12 47 29 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/ae4928c9-48b8-4861-af42-acf1908947f2">

# 2024-04-10 - Received and Programmed pcb

Received the printed circuit boards (PCBs) from the manufacturer. We used the flow iron to solder the parts onto the PCB. We also had to hand solder some of the parts such as the connector.

<img width="382" alt="Screen Shot 2024-05-02 at 12 43 11 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/345defc6-97d4-4f4d-9fff-29d6ee5954cd">

# 2024-04-15 - Helping finish up CNN
Convolutional Neural Networks (CNN): The development of our machine learning capabilities begins with the application of CNNs, which help identify differences between pulsatile and continuous flow patterns. The CNN's is good at analyzing visual representations of these flow patterns in the spectral data, which makes it effective at classifying the type of flow based on its characteristics. 
We needed more fake samples of data for continuous and pulsatile flow as the quality of the training data directly impacts the accuracy and reliability.​ We created an algorithm that gave us around 15000 different data points to distinguish between pulsatile and continuous flow.​
The increase in samples helped increase the accuracy and reliability of the CNN as shown through the Precision, Recall, and F1-score.​

<img width="484" alt="Screen Shot 2024-05-02 at 12 44 05 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/8dae402e-f461-4952-8808-68a03a787848">
