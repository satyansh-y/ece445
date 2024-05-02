# Rishab Worklog

This worklog contains the progress of a PCB design project aimed at developing a medical device that records audio and transmits it via Bluetooth to a smartphone application. Below are key milestones and updates:

# 2024-01-29 - Meeting with Richard and Eric from Carle College of Medicine

We met with Richard and Eric to discuss the intricacies of their pitched project and clear up any of our doubts regarding the vision for the solution. Afterward, we created and submitted our RFA to the web board.

# 2024-02-01 - Research and Initial Timeline

We created a rough timeline for the remainder of the semester to have an idea of how we would go about finishing this project. We spent some time researching what components we definitely would need for our PCB.

# 2024-02-05 - Initial Brainstorming and Approval

The project kicked off with an initial brainstorming session where the concept of a medical device capable of recording and transmitting audio was discussed and approved. Objectives were set, and preliminary designs were drafted. We set the requirements and each person claimed what they wanted to work on and planned out the required technology. I focused primarily on the control and LED subsystem of the PCB. I heavily focused on getting fake samples of data as machine learning models depend on data. Without a foundation of high-quality training data, even the most performant algorithms can be rendered useless. Indeed, robust machine learning models can be crippled when they are trained on inadequate, inaccurate, or irrelevant data in the early stages. I also had to focus on our CNN and these fake samples made sure we would have enough training samples to help increase the accuracy and reliability of the CNN as shown through the Precision, Recall, and F1-score. 

# 2024-02-07 - Project Proposal

We received feedback from Richard and our TA Surya related to what we would need in our block diagram and what our high-level requirements would be.
Finally, we began working on our project proposal which is due on 02/08.

<img width="512" alt="Screen Shot 2024-05-02 at 12 57 56 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/a527dcc4-7a33-4d44-8d55-c2899e9f68b4">

Figure 1: Arteriovenous Fistula Monitoring Device General Design

# 2024-02-12 - Beginning Design of PCB

After doing more research on PCB development, we began with making a components list of what we would need. 


# 2024-02-19 - Research for Control Subsystem

For the device's power subsystem, I integrated a microUSB port, opting for it as a direct power supply solution. The heart of this subsystem is the TPS79333-EP, a linear voltage regulator chosen for its ability to provide stable and reliable power. This steps the voltage down from 5V which is the input voltage to 3.3V which is what the parts of our board operate on. To address the challenge of high-frequency noise, which could potentially disrupt the device's sensitive readings, I engineered a noise rejection circuit. This circuit is built around a ferrite bead, the BLM18G101TN1D, known for its effectiveness in filtering high-frequency noise. Alongside this, I incorporated two 1nF capacitors in parallel, enhancing the circuit's ability to maintain a clean power supply by further smoothing out any residual electronic disturbances. This approach ensures that the device operates with optimal precision and reliability.

<img width="657" alt="Screen Shot 2024-05-02 at 1 11 11 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/a7803c8b-f2f8-421f-8fb4-28f66b38d029">

<img width="655" alt="Screen Shot 2024-05-02 at 1 11 49 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/08453129-43dd-4397-92cc-1500dd07683d">

<img width="508" alt="Screen Shot 2024-05-02 at 1 13 40 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/7bcf6c95-059a-43fc-baf5-650f9f95872c">

# 2024-02-23 - Finishing PCB Design for Control Subsystem

Nina B306 processor
The processor is picked out because of its high flash storage characteristic as well as its built-in bluetooth antenna. This is incredibly useful because it does not require a separate circuit for a bluetooth connection. The board comes with Bluetooth 5 Low energy which is sufficient for audio transmission.

Incorporating an Electrostatic Discharge (ESD) protection circuit into our device was a critical step to ensure its longevity and reliability, especially in a medical setting where it will be subjected to various environmental factors that could potentially cause damage. For this purpose, we chose the PRTR5V0U2X series for ESD protection, a decision driven by its robust performance in safeguarding sensitive electronic components against the abrupt and potentially damaging effects of ESD events.:
Dual-Line Protection: The PRTR5V0U2X offers protection for two lines with a single component, making it an efficient choice for compact PCB designs where space is at a premium. This is particularly important in wearable medical devices, where minimizing size without compromising on protection is crucial.
Low Clamping Voltage: This ESD protection device has a low clamping voltage, which means it can effectively clamp down on the voltage during an ESD event to a level that is safe for the sensitive electronics in our device. This is essential for preventing damage that could lead to device failure or inaccurate readings.
High Surge Capability: The component is capable of handling significant surge currents, ensuring that even in the case of a strong ESD event, the protection circuit can absorb the excess energy without being damaged itself.

<img width="327" alt="Screen Shot 2024-05-02 at 1 14 20 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/1623875e-cfb2-4f01-8839-22395987f204">

<img width="299" alt="Screen Shot 2024-05-02 at 1 12 49 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/d6da386e-81a5-45ac-b93b-a0f9191741af">

# 2024-02-29 - Power LED Subsystem

A status indicator LED was added to the design in order to show when the device is recording for privacy reasons as well as when the device is turned on. This provides a quick indicator that doesn't require software for debugging and patient interaction. 

<img width="485" alt="Screen Shot 2024-05-02 at 1 15 30 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/f9828410-13c8-4b54-a97d-031476d53b2e">

# 2024-03-07 - Finishing touches on PCB Design and beginning ordering

At this point I have finished up the PCB and looked through everything multiple times. Our team was ready to put in orders and since we were a pitched project we had a lot of funding. Due to this, we put in orders for multiple PCBs with different microphones as we didn't actually know which microphone would perform the best. Below is a screenshot of the remaining parts that we ordered this week. We also placed a PCB order.

<img width="1351" alt="Screen Shot 2024-05-02 at 1 04 01 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/e784c1e2-0b61-47a2-8b1c-40d4b9f7cbe8">

# 2024-03-25 - Create an algorithm that creates fake samples of continuous and pulsatile flow

We needed more fake samples of data for continuous and pulsatile flow as the quality of the training data directly impacts the accuracy and reliability.​ I created an algorithm that gave us around 15000 different data points to distinguish between pulsatile and continuous flow.​
The increase in samples helped increase the accuracy and reliability of the CNN as shown through the Precision, Recall, and F1-score later on.

# 2024-04-03 - Used fake samples of data to train CNN

<img width="434" alt="Screen Shot 2024-05-02 at 1 20 20 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/08dce4be-d98f-4988-9ec4-b2c5ac063095">

<img width="434" alt="Screen Shot 2024-05-02 at 1 20 31 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/fef13ebe-5172-46f4-b712-825357aae8f0">

# 2024-04-10 - Received and Programmed pcb

Received the printed circuit boards (PCBs) from the manufacturer. We used the flow iron to solder the parts onto the PCB. We also had to hand solder some of the parts such as the connector.

<img width="382" alt="Screen Shot 2024-05-02 at 12 43 11 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/345defc6-97d4-4f4d-9fff-29d6ee5954cd">

# 2024-04-15 - Finished up CNN and will continue working on this as a start-up
Model Training and Validation
I utilized a split of training and validation datasets to train the CNN model, ensuring they accurately classify pulsatile and continuous flow patterns. The validation dataset, unseen by the model during training, will test the model's ability to generalize to new data.

Cross-Validation
I employed k-fold cross-validation to assess the model's performance across different subsets of the dataset, ensuring reliability and reducing the likelihood of overfitting.

The development of our machine learning capabilities begins with the application of CNNs, which help identify differences between pulsatile and continuous flow patterns. I used precision to evaluate the model's ability to correctly identify instances of AVF condition changes (e.g., onset of stenosis or thrombosis) from the audio signals, minimizing false alarms.
Recall measures the proportion of actual positives correctly identified by the model. It assesses the model's ability to capture all relevant cases of condition changes
F1 Score is the harmonic mean of precision and recall. It balances the two metrics, providing a single measure to assess the model's overall accuracy.
Application: The F1 Score will be used to evaluate the model's balanced performance in correctly identifying AVF condition changes while avoiding false positives and negatives.

<img width="484" alt="Screen Shot 2024-05-02 at 12 44 05 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/8dae402e-f461-4952-8808-68a03a787848">

<img width="881" alt="Screen Shot 2024-05-02 at 1 21 29 PM" src="https://github.com/satyansh-y/ece445/assets/92760614/09021993-2a21-43ec-a1cd-0d0a4534dee4">
