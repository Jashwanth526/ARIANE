# ARIANE
# Automated Reusable Indigenous Aero-Navigating Extraterrestrial Vehicle (ARIANE)

This is a mini-project report for the "Automated Reusable Indigenous Aero-Navigating Extraterrestrial Vehicle" (ARIANE), a reusable rocket prototype. This project was submitted in partial fulfillment for the Award of the Degree of Bachelor of Engineering in Electronics and Communication Engineering at RNS Institute of Technology.



## About This Project

This project focuses on the development of reusable rockets, which are a revolutionary step in making space exploration more affordable, efficient, and sustainable. Traditional rockets are designed for single use, making space missions very expensive. This project's reusable rocket is engineered to be launched, recovered, and launched again multiple times, significantly reducing costs.

The report examines the key technologies required, such as advanced engines, thermal protection, and automated landing systems. A critical aspect is the ability to control the rocket during its return to Earth for a safe landing and refurbishment. The project studies successful examples like SpaceX's Falcon 9 and includes simulations to test the performance of proposed designs.

## Key Objectives

The primary objectives of this project were:

* **Design & Build:** To design and build a 3.5-foot solid propellant rocket.
* **Propulsion:** To implement a solid propellant system using D-Sorbitol and potassium nitrate (KNO3).
* **Control System:** To design and integrate a Thrust Vector Control (TVC) mechanism for precise maneuverability and flight path adjustments.
* **Avionics:** To create and test electronic components, including sensors, actuators, and microcontrollers, for real-time flight control.
* **Analysis:** To conduct structural and thermal analysis to ensure integrity during flight.
* **Validation:** To conduct ground and flight tests to validate the performance of the entire system.

## Hardware Configuration

The following hardware components were used to build the rocket's avionics and control system:

* **Main Computer:** **Teensy 4.1** Microcontroller
* **Positioning:** **Adafruit Ultimate GPS Feather Wing** (MTK3333 chipset)
* **Data Logging:** **Adafruit Adalogger Feather Wing** (PCF8523 RTC and microSD)
* **Actuation:** **Adafruit 8-Channel PWM Servo Feather Wing**
* **Navigation:** **SparkFun ICM20948 9-axis IMU** (Accelerometer, Gyroscope, Magnetometer)
* **Altitude:** **DFRobot BMP388** Barometric Pressure Sensor
* **Power:** **1500mAh 3S LiPo Battery**

## Software & System Methodology

The rocket's autonomous flight control system is built on custom firmware and several key libraries.

### Software & Libraries
* **Firmware:** Developed for the **Teensy 4.1** using the Arduino IDE and Teensyduino add-on.
* **Adafruit GPS Library:** For parsing NMEA data from the GPS module.
* **Adafruit Servo Library:** For generating PWM signals to control the TVC servos.
* **SparkFun ICM20948 Library:** For reading accelerometer, gyro, and magnetometer data.
* **DFRobot BMP388 Library:** For accurate barometric pressure and altitude readings.
* **Adafruit RTC Library:** For precise data logging timestamps.

### Control System
The system's methodology relies on a closed-loop control system to maintain stability:

1.  **Sensor Fusion:** A **Kalman filter** is implemented in the code to process noisy altitude readings from the BMP388 pressure sensor, providing a much more accurate and stable altitude estimate.
2.  **State Estimation:** The **ICM20948 IMU** detects the rocket's orientation and any angular displacements (i.e., if it starts to tip over).
3.  **PID Control:** A **PID (Proportional-Integral-Derivative) controller** calculates the necessary correction based on the error between the desired setpoint (flying straight) and the actual orientation measured by the IMU.
4.  **Actuation:** The PID controller's output commands the **Adafruit Servo FeatherWing** to move the servos. These servos physically adjust the **TVC gimbal mount**, changing the angle of the engine's thrust to steer the rocket back to a stable trajectory.

## Project Outcome

The project successfully met its primary objectives by developing a reusable TVC solid-propellant rocket.

* **Apogee:** The rocket successfully achieved its target **apogee (maximum altitude) of 100 feet**.
* **Stability:** The TVC system, built with an Aluminum 6065 mount, proved durable and effectively stabilized the rocket during ascent. The servos successfully provided thrust alignment within **$\pm5^{\circ}$ on the X and Y axes**.
* **Control System:** The IMU, Kalman filter, and PID control algorithms worked in conjunction to provide reliable altitude estimation and counteract angular displacements.
* **Area for Improvement:** A minor delay was observed in the ignition of the second motor during the descent phase, which was attributed to a small lag in the altitude estimation and ignition circuitry. This was identified as an area for future optimization.



## Authors

* **JASHWANΤΗ Κ** (1RN22EC048)
* **VISHNU JOSHI** (1RN22EC142)
* **DHANVI ACHARYA** (1RN22EC039)
* **JATHEEN V** (1RN22EC049)

## Acknowledgments

* **Project Guide:** Mr. Sreenivasa Babu MO, Assistant Professor, Department of ECE.
* **Institution:** RNS Institute of Technology, Bengaluru (Affiliated to Visvesvaraya Technological University).
* **Department:** Department of Electronics and Communication Engineering.
