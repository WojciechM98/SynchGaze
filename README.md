# SynchGaze
PC Keyboard with embedded functionality for fast prototyping and testing external devices.


## Project assumptions
The project includes two boards SynchGaze Transmiter and SynchGaze Motor Control that communicate with each other via bluetooth.

## SynchGaze Transmiter
Transmiter board has IMU device to collect position, acceleration and rotation data. Every information is preprocessed and send in real time by ESP32 to Motor Control board.
This board should be neatly attached to the user's head.

![Alt text](SynchGaze_Transmiter/SynchGaze_Transmiter.png?raw=true "SynchGaze Transmiter board.")

## SynchGaze Motor Control
Motor Control board recieve preprocessed data from Transmiter and converts it into BLDC motors movement. STM32 works in closed loop gathering data from external IMU device whith is attached in the same place as camera. When new information from Transmiter board is recieved the possition according to external IMU is corrected by sending information about revolutions and acceleration to specific motor controler.

![Alt text](SynchGaze_Motor_Control/SynchGaze_Motor_Control.png?raw=true "SynchGaze Motor Control board.")


