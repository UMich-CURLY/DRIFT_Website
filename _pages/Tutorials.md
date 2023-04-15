---
permalink: /tutorials/
author_profile: true
---

# Getting Started/Learn to use the DRIFT library

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
1. Measurements: The Measurements component includes classes to represent different types of sensor data relevant for state estimation. The primary class, "Measurement," serves as a base class for specific measurement types, such as ImuMeasurement (for IMU readings) and ContactMeasurement (for legged robot foot contact states). These classes store time-sequential sensor data in a queue, ready to be processed by the filter.

<img src="/images/measurement.png" alt= measurement style="max-width:85%;height:auto">

2. Filter: The Filter component is the core of the library, where the Invariant Extended Kalman Filter (InEKF) algorithm is implemented. This component takes the robot's current state and incoming measurements to predict and correct the estimates of the robot's position, orientation, and velocity. 

<img src="/images/filter.png" alt= filter style="max-width:85%;height:auto">

3. Filter Interface: The Filter Interface is designed to simplify the integration of the InEKF into your project. It provides an abstraction layer between users and the underlying filter implementation, making it easier to use the library without in-depth knowledge of InEKF. The main class in this component is the StateEstimator, which offers methods for adding propagation and correction steps based on the available incoming sensor data.

<img src="/images/filterinterface.png" alt= filterinterface style="max-width:85%;height:auto">

4. Robot State: The Robot State component holds information about the current state of the robot, including position, velocity, orientation, state covariance, and sensor biases. This state is used as input for the filter during the prediction step and gets updated with refined estimates after processing the incoming measurements.

<img src="/images/robotstate.png" alt= rstate style="max-width:85%;height:auto">

5. Robot Kinematics Interface: This component is only necessary for legged robots and stores the kinematic definition of a particular robot, such as a quadrupedal configuration. The Robot Kinematics Interface is responsible for computing the body-frame position, which is combined with foot contact information and used in the Kalman filter's correction step. 

<img src="/images/kin.png" alt= kin style="max-width:85%;height:auto">

6. Communication Interface: The Communication Interface serves as the outermost wrapper, managing communication between the library and external sources or sinks. This component ensures that the library can easily receive measurement data streams and transmit the updated state estimates for use elsewhere. For DRIFT, we have provided interface wrappers for ROS, ROS 2, and Lightweight Communications Marshalling (LCM). Alternatively, the library headers are made available for implementing a custom communication method (over UDP for example).

<img src="/images/comm.png" alt= comm style="max-width:85%;height:auto">

Below is DRIFT's flow structure of data input and robot state information output.

<img src="/images/flowdiagram.png" alt= flow style="max-width:85%;height:auto">

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

Provide a examples or use cases to demonstrate the library's functionality in real-world scenarios.

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

<!--
### Cartesian Dataset
* <b>Train</b> 
    * <a href="https://www.dropbox.com/s/colr0tqiqcwiuto/train_cartesian_13.zip?dl=0">Download 40.3GB</a> (Town 01-03)
    * <a href="https://www.dropbox.com/s/cm0qhmcwj1mz2tx/train_cartesian_46.zip?dl=0">Download 39.7GB</a> (Town 04-06)

* <b>Validation</b> 
    * <a href="https://www.dropbox.com/s/6aazdgg71n2aa0y/val_cartesian.zip?dl=0">Download 14.9GB</a>

* <b>Test</b> 
    * <a href="https://www.dropbox.com/s/4aprfo1zdg4g57z/test_cartesian.zip?dl=0">Download 14.6GB</a>


### Cartesian Finer Dataset
* <b>Train + Validation + Test</b>
    * <a href="https://www.dropbox.com/s/9d78c3hqxf6iwvy/eval_fine.zip?dl=0">Download 4.3GB</a>

### Cylindrical Dataset
* <b>Train + Validation + Test</b>
    * <a href="https://www.dropbox.com/s/eb074zjfilri1ka/eval_cylindrical.zip?dl=0">Download 3.8GB</a>


<font size="3">Note: If you can't access the files using the above links, you can try the alternate links below. They are separated into specific folders to reduce file size. If neither work, please try again after 24 hr.</font> 
    

## Alternate Links


* ### Velodyne

    * <b>Train</b>
        * Town 01 (<a href="https://drive.google.com/file/d/1ZYuDLUJmsKG0njoMSjIjPgdDaz9U6LXX/view?usp=sharing">Download 5.8GB</a>) 
        * Town 02 (<a href="https://drive.google.com/file/d/1h5u6bCXX8qkNoB0PG_zjO56EgPYH5wVp/view?usp=sharing">Download 6.4GB</a>)
        * Town 03 (<a href="https://drive.google.com/file/d/1gzEGAVblhzsMngjGGXAIOURgRDlKmOQY/view?usp=sharing">Download 6.4GB</a>)
        * Town 04 (<a href="https://drive.google.com/file/d/1fTlkzZrAA9BKGOTmzjAfrNZPO9uPNbA5/view?usp=sharing">Download 5.6GB</a>)
        * Town 05 (<a href="https://drive.google.com/file/d/1Omkm9OFMOdkSDcJ5DMILjhmzdXZp2EtA/view?usp=sharing">Download 6.5GB</a>)
        * Town 06 (<a href="https://drive.google.com/file/d/1QHrcPoU5zuahH4b6PH3V-Mb5d2o335c4/view?usp=sharing">Download 6.0GB</a>)

    * <b>Validation</b>
        * Town 07 (<a href="https://drive.google.com/file/d/1CNqqVIbRP8iF4gUYHU-ZmFUnk3tdB50E/view?usp=sharing">Download 6.4GB</a>) 

    * <b>Test</b>
        * Town 10 (<a href="https://drive.google.com/file/d/15ewAhsfpeo30O4f8o1tj1hmNEhiklUVo/view?usp=sharing">Download 6.5GB</a>) 

* ### Labels

    * <b>Train</b>
        * Town 01 - 06 (<a href="https://drive.google.com/file/d/1_6r8Ebl9EsvFAfvyKDtyUrORt4ihK-BC/view?usp=sharing">Download 99MB</a>) 


    * <b>Validation</b>
        * Town 07 (<a href="https://drive.google.com/file/d/1CGGxkK4nZHG1ToZ_WMq0gPzq9kerPRPq/view?usp=sharing">Download 22MB</a>) 

    * <b>Test</b>
        * Town 10 (<a href="https://drive.google.com/file/d/17r3u4cS7U2wA11NUI7yV5p2s0TCePjXJ/view?usp=sharing">Download 23MB</a>) 


* ### Evaluation

    * <b>Train</b>
        * Cartesian (<a href="https://drive.google.com/file/d/1dDjhtPasGX51YBM63mhRc9bf4uEftoyJ/view?usp=sharing">Download 2.6GB</a>)
        * Cartesian Fine (<a href="https://drive.google.com/file/d/1dPSpFq3DqGxwsIJ5SgY8D6-TBUMbV9RO/view?usp=sharing">Download 3.2GB</a>)
        * Cylindrical (<a href="https://drive.google.com/file/d/1ZN9JYV98K2L4JMgKWlsGy2EE_bPRnCl8/view?usp=sharing">Download 2.8GB</a>)


    * <b>Validation</b>
        * Cartesian (<a href="https://drive.google.com/file/d/1hpz44LbZvSv6E0iCukKsUsjD71_c1czA/view?usp=sharing">Download 473MB</a>)
        * Cartesian Fine (<a href="https://drive.google.com/file/d/1rKVu3coFS7HfZNAieKp6Y0biFbKmQE2i/view?usp=sharing">Download 574MB</a>)
        * Cylindrical (<a href="https://drive.google.com/file/d/1C0VBNxzernOWXVqDDJ7usrUU7ZC6Fp_c/view?usp=sharing">Download 497MB</a>)

    * <b>Test</b>
        * Cartesian (<a href="https://drive.google.com/file/d/1KBWuIpO2-KTSNpGlGPLDMZv58wTiqh9W/view?usp=sharing">Download 484MB</a>)
        * Cartesian Fine (<a href="https://drive.google.com/file/d/1Oy-XB6jMrtrrAcmOda0Y9NC_kAC5-3Yx/view?usp=sharing">Download 510MB</a>)
        * Cylindrical (<a href="https://drive.google.com/file/d/1eKY52FSNX2kJe6RxhAiBxeh_YDoLbewB/view?usp=sharing">Download 505MB</a>)


* ### Predictions

    * <b>Train</b>
        * Town 01 - 06 (<a href="https://drive.google.com/file/d/1R0EZMlehUCh4sKjcCWdZyH6Ez75wbGsX/view?usp=sharing">Download 68MB</a>) 


    * <b>Validation</b>
        * Town 07 (<a href="https://drive.google.com/file/d/1Fuih2nOKo4oG8F3S4OzbvxUy9sP1cQ1I/view?usp=sharing">Download 13MB</a>) 

    * <b>Test</b>
        * Town 10 (<a href="https://drive.google.com/file/d/1dtGMiG6NxhIlif2sDTUwIZFtRMehZPNo/view?usp=sharing">Download 14MB</a>) 


* ### BEV

    * <b>Train</b>
        * Town 01 (<a href="https://drive.google.com/file/d/14rN7_AGYhOPsfbn-7zw9yqFD0wtS6zzt/view?usp=sharing">Download 5.9GB</a>) 
        * Town 02 (<a href="https://drive.google.com/file/d/11oFuNA3hRZaxg4GFBYaoECr2P34dm6hF/view?usp=sharing">Download 7.4GB</a>)
        * Town 03 (<a href="https://drive.google.com/file/d/1-cmt4UnZMghpQxYGBj5D3FOj_09ALtb-/view?usp=sharing">Download 6.8GB</a>)
        * Town 04 (<a href="https://drive.google.com/file/d/1crYbaiWahBR9xlpiQpmNhTcCNU6kmBMb/view?usp=sharing">Download 6.2GB</a>)
        * Town 05 (<a href="https://drive.google.com/file/d/1dRUWeoeMZeES6IDwPcrp6UIhK6kHZSlL/view?usp=sharing">Download 6.6GB</a>)
        * Town 06 (<a href="https://drive.google.com/file/d/1r78E3pY0P-4ExzxaO5q69kQeb_yHu-QG/view?usp=sharing">Download 7.1GB</a>)

    * <b>Validation</b>
        * Town 07 (<a href="https://drive.google.com/file/d/1TnTm-sThHhngqrhWyHm5mFkP_kXk-gX9/view?usp=sharing">Download 7.9GB</a>) 

    * <b>Test</b>
        * Town 10 (<a href="https://drive.google.com/file/d/1Xwj8NfedNk2K4emfJpAoA7PUyhotV_JV/view?usp=sharing">Download 7.6GB</a>) 


## Models
<div class="DOWNLOAD-block">
    <a href="https://github.com/UMich-CURLY/3DMapping">MotionSC Github Repository</a>
</div>
<div class="DOWNLOAD-block">
    <a href="https://github.com/UMich-CURLY/3DMapping/tree/main/Models/Weights">MotionSC Model Weights (Pytorch)</a>
</div>
-->