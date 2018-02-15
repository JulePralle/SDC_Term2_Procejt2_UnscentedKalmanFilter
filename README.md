# Unscented Kalman Filter 

Self-Driving Car Engineer Nanodegree Program

--

[//]: # (Image References)

[image1]: ./EKFvsUKF.png "Example EKF vs UKF"


## Introduction
In this project an unscented Kalman filter was utilized to estimate the state of a moving object in the udacity simulator with noisy lidar and radar measurements for reaching a better accurancy and performance than an extended Kalman filter [(last project)](https://github.com/JulePralle/SDC_Term2_Project1_ExtendedKalmanFilter) is capable of. 


## Extended (EKF) vs. Unscented Kalman Filter (UKF)
* The Unscented Kalman filter is an alternative technique to deal with non-linear models
* Instead of linearizing a non-linear function as the EKF does, the UKF uses sigma points to approximate the probability distribution
* with this technique the UKF is capable of providing a more smooth position and velocity estimation of dynamic objects without introducing a delay

The images below compare the estimation of an dynamic moving object with an EKF (left) and an UKF (right). Die estimation of the EKF underestimates the truth state and the estimation of the UKF follows the ground truth much better.

![alt text][image1]


## Files and code
#### [/src/main.cpp:](https://github.com/JulePralle/SDC_Term2_Project2_UnscentedKalmanFilter/blob/master/src/main.cpp)
* reads in the data
* calls a function to run the Unscented Kalman filter
* calls a function to calculate the RMSE
 
#### [/src/ukf.cpp:](https://github.com/JulePralle/SDC_Term2_Project2_UnscentedKalmanFilter/blob/master/src/ukf.cpp)
* initializes the Unscented Kalman filter
* calls the predict function
* calls the update function
* defines the predict and update functions

#### [/src/tools.cpp:](https://github.com/JulePralle/SDC_Term2_Project2_UnscentedKalmanFilter/blob/master/src/tools.cpp)
* function to calculate the RMSE 


# Udacity Part
---
## Project Starter Code

This project involves the Term 2 Simulator which can be downloaded [here](https://github.com/udacity/self-driving-car-sim/releases)

This repository includes two files that can be used to set up and intall [uWebSocketIO](https://github.com/uWebSockets/uWebSockets) for either Linux or Mac systems. For windows you can use either Docker, VMware, or even [Windows 10 Bash on Ubuntu](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/) to install uWebSocketIO. 

Once the install for uWebSocketIO is complete, the main program can be built and ran by doing the following from the project top directory.

1. mkdir build
2. cd build
3. cmake ..
4. make
5. ./UnscentedKF

Note that the programs that need to be written to accomplish the project are src/ukf.cpp, src/ukf.h, tools.cpp, and tools.h

The program main.cpp has already been filled out, but feel free to modify it.

Here is the main protcol that main.cpp uses for uWebSocketIO in communicating with the simulator.


INPUT: values provided by the simulator to the c++ program

["sensor_measurement"] => the measurment that the simulator observed (either lidar or radar)


OUTPUT: values provided by the c++ program to the simulator

["estimate_x"] <= kalman filter estimated position x
["estimate_y"] <= kalman filter estimated position y
["rmse_x"]
["rmse_y"]
["rmse_vx"]
["rmse_vy"]

---

## Other Important Dependencies

* cmake >= v3.5
* make >= v4.1
* gcc/g++ >= v5.4

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./UnscentedKF path/to/input.txt path/to/output.txt`. You can find
   some sample inputs in 'data/'.
    - eg. `./UnscentedKF ../data/obj_pose-laser-radar-synthetic-input.txt`

## Editor Settings

We've purposefully kept editor configuration files out of this repo in order to
keep it as simple and environment agnostic as possible. However, we recommend
using the following settings:

* indent using spaces
* set tab width to 2 spaces (keeps the matrices in source code aligned)

## Code Style

Please stick to [Google's C++ style guide](https://google.github.io/styleguide/cppguide.html) as much as possible.

## Generating Additional Data

This is optional!

If you'd like to generate your own radar and lidar data, see the
[utilities repo](https://github.com/udacity/CarND-Mercedes-SF-Utilities) for
Matlab scripts that can generate additional data.

## Project Instructions and Rubric

This information is only accessible by people who are already enrolled in Term 2
of CarND. If you are enrolled, see [the project page](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/0949fca6-b379-42af-a919-ee50aa304e6a/lessons/c3eb3583-17b2-4d83-abf7-d852ae1b9fff/concepts/f437b8b0-f2d8-43b0-9662-72ac4e4029c1)
for instructions and the project rubric.
