---
permalink: /tutorials/
title: Getting Started - Learn to use the DRIFT library
author_profile: true
---

This Getting Started tutorial will help you quickly set up and start using the library, even if you're not familiar with the underlying concepts of Invariant Extended Kalman Filtering (InEKF).

For more detailed information on the DRIFT library, see the <a href="https://umich-curly.github.io/DRIFT_Website/doxygen/html/index.html" target="_blank">core DRIFT documentation</a>.

## Finding Code
DRIFT Source code is on Github: <a href="https://github.com/UMich-CURLY/drift" target="_blank">https://github.com/UMich-CURLY/drift</a>. Issues can also be opened there.

## Introduction

This library is designed to provide accurate and reliable state estimation (odometry) for grounded mobile robots, including legged and wheeled platforms. It is built around an advanced probabilistic technique called Invariant Extended Kalman Filtering (InEKF) that estimates the position and velocity of a robot by predicting the robot state and correcting the prediction via available sensor data (IMU, legged robot joint encoders, wheel rotary encoders, etc.). 

## Prerequisites

TODO: List the required software components.
Provide information on how to install any necessary dependencies. Maybe provide a terminal command(s) to install dependencies easily.

## Library Overview

There are 6 core components that make up the DRIFT library:
1. **Measurements**: The Measurements component includes classes to represent different types of sensor data relevant for state estimation. The primary class, "Measurement," serves as a base class for specific measurement types, such as ImuMeasurement (for IMU readings) and ContactMeasurement (for legged robot foot contact states). These classes store time-sequential sensor data in a queue, ready to be processed by the filter.

<div align="center"><img src="{{ site.url }}/DRIFT_Website/images/measurement.png" alt= measurement style="max-width:30%;height:auto"></div>

2. **Filter**: The Filter component is the core of the library, where the Invariant Extended Kalman Filter (InEKF) algorithm is implemented. This component takes the robot's current state and incoming measurements to predict and correct the estimates of the robot's position, orientation, and velocity. 

<div align="center"><img src="{{ site.url }}/DRIFT_Website/images/filter.png" alt= filter style="max-width:85%;height:auto"></div>

3. **Filter Interface**: The Filter Interface is designed to simplify the integration of the InEKF into your project. It provides an abstraction layer between users and the underlying filter implementation, making it easier to use the library without in-depth knowledge of InEKF. The main class in this component is the StateEstimator, which offers methods for adding propagation and correction steps based on the available incoming sensor data.

<div align="center">
<img src="{{ site.url }}/DRIFT_Website/images/filterinterface.png" alt= filterinterface style="max-width:25%;height:auto"></div>

4. **Robot State**: The Robot State component holds information about the current state of the robot, including position, velocity, orientation, state covariance, and sensor biases. This state is used as input for the filter during the prediction step and gets updated with refined estimates after processing the incoming measurements.

<div align="center"><img src="{{ site.url }}/DRIFT_Website/images/robotstate.png" alt= rstate style="max-width:20%;height:auto"></div>

5. **Robot Kinematics Interface**: This component is only necessary for legged robots and stores the kinematic definition of a particular robot, such as a quadrupedal configuration. The Robot Kinematics Interface is responsible for computing the body-frame position, which is combined with foot contact information and used in the Kalman filter's correction step. 

<div align="center"><img src="{{ site.url }}/DRIFT_Website/images/kin.png" alt= kin style="max-width:85%;height:auto"></div>

6. **Communication Interface**: The Communication Interface serves as the outermost wrapper, managing communication between the library and external sources or sinks. This component ensures that the library can easily receive measurement data streams and transmit the updated state estimates for use elsewhere. For DRIFT, we have provided interface wrappers for ROS, ROS 2, and Lightweight Communications Marshalling (LCM). Alternatively, the library headers are made available for implementing a custom communication method (over UDP for example).

<div align="center"><img src="{{ site.url }}/DRIFT_Website/images/comm.png" alt= comm style="max-width:85%;height:auto"></div>


Below is DRIFT's flow structure of data input and robot state information output.

<div align="center"><img src="{{ site.url }}/DRIFT_Website/images/flowdiagram.png" alt= flow style="max-width:85%;height:auto"></div>

TODO: Break down the process of using the library into smaller, manageable steps. For each step, provide clear instructions and code snippets, if applicable.

Steps can include:
a. Initializing the library
b. Configuring robot-specific settings (e.g., kinematics for legged robots)
c. Creating Measurement objects (e.g., ImuMeasurement, ContactMeasurement)
d. Sending measurements to the Filter Interface (StateEstimator)
e. Accessing the estimated Robot State
f. Integrating the library with your specific robot system

Be sure to include explanations and context for each step, so users understand the purpose behind the actions they are taking.

## Examples and use cases

Provide examples or use cases to demonstrate the library's functionality in real-world scenarios.

Include sample code and explanations for each example to help users see the library in action and better understand how to apply it to their own projects.

## Troubleshooting and FAQs

Can possibly make this a separate page linked to the main site.

List common issues or questions that users may encounter while working with the library, along with their solutions or explanations.

This section can be updated over time as you receive user feedback and questions.

## Further reading and resources

TODO: Provide links to relevant documentation, papers, or other resources for users who want to learn more about InEKF or dive deeper into the library's capabilities.

## Conclusion

TODO: Recap the key points covered in the tutorial.
Encourage users to provide feedback or ask questions to improve the library and its documentation.

<hr>
### <a href="https://umich-curly.github.io/DRIFT_Website/doxygen/html/md__home_tingjunl_code_curly_state_estimator_doc_tutorial_inekf_imu_and_legged_kin_ros.html" target="_blank">[ROS] InEKF, IMU + Legged Kinematics Tutorial</a> 
<hr>
### <a href="https://umich-curly.github.io/DRIFT_Website/doxygen/html/md__home_tingjunl_code_curly_state_estimator_doc_tutorial_inekf_imu_and_vel_ros.html" target="_blank">[ROS] InEKF, IMU + Velocity Tutorial</a> 
<hr>
### <a href="https://umich-curly.github.io/DRIFT_Website/doxygen/html/md__home_tingjunl_code_curly_state_estimator_doc_tutorial_inekf_imu_and_vel_ros.html" target="_blank">Custom Legged Kinematics Class Tutorial</a> 
<hr>
