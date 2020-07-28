# Extended Kalman Filter Project
Self-Driving Car Engineer Nanodegree Program


Autonomous Vehicles need to rely on different sensors to sense their environment and estimate their state in their environment accurately. Autonomous Vehicles mostly rely on 3 important sensors, Camera, LIDAR and RADAR. While Cameras are mostly used to sense the environment and observe their surroundings, LIDARs and RADARs are mostly used to estimate the state of the vehicle and its surrounding objects in the environment which mainly include position, velocity and sometimes acceleration too.

However these sensors are sometimes not extremely accurate and produce a lot of noise, which can lead to catastrophic events in the state of inaccuracies. Kalman Filters suppresses the noise produce by the sensors and provide really accurate result about the state of the vehicle. Kalman Filters uses a series of measurements observed over time, containing statistical noise and other inaccuracies, and produces estimates of unknown variables that tend to be more accurate than those based on a single measurement alone, by estimating a joint probability distribution over the variables for each timeframe.

The algorithm works in a two-step process. In the prediction step, the Kalman filter produces estimates of the current state variables, along with their uncertainties. Once the outcome of the next measurement (necessarily corrupted with some amount of error, including random noise) is observed, these estimates are updated using a weighted average, with more weight being given to estimates with higher certainty. 


In this project, I utilized a Extended Kalman Filter to estimate the state of a moving object of interest with noisy lidar and radar measurements. As you can see in the video, data from the LIDAR is presented in blue circles,  the red circles with the arrow pointing towards the direction of the observed angle represents data from the RADAR and estimation markers are green triangles. 


[image1]: ./ezgif.com-video-to-gif.gif
![image][image1]

This project involves the Term 2 Simulator which can be downloaded [here](https://github.com/udacity/self-driving-car-sim/releases)

This repository includes two files that can be used to set up and install [uWebSocketIO](https://github.com/uWebSockets/uWebSockets) for either Linux or Mac systems. For windows you can use either Docker, VMware, or even [Windows 10 Bash on Ubuntu](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/) to install uWebSocketIO. Please see the uWebSocketIO Starter Guide page in the classroom within the EKF Project lesson for the required version and installation scripts.

Once the install for uWebSocketIO is complete, the main program can be built and run by doing the following from the project top directory. The file is currently already built, so you can skip steps 2 and 3.

1. cd build
2. cmake ..
3. make
4. ./ExtendedKF


INPUT: values provided by the simulator to the c++ program

["sensor_measurement"] => the measurement that the simulator observed (either lidar or radar)


OUTPUT: values provided by the c++ program to the simulator

["estimate_x"] <= kalman filter estimated position x
["estimate_y"] <= kalman filter estimated position y
["rmse_x"]
["rmse_y"]
["rmse_vx"]
["rmse_vy"]

---

## Other Important Dependencies

* cmake >= 3.5
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build` (Can skip this part, if no changes are made)
3. Compile: `cmake .. && make` (Can skip this part, if no changes are made)
   * On windows, you may need to run: `cmake .. -G "Unix Makefiles" && make`
4. Run it: `./ExtendedKF `

## Editor Settings

We've purposefully kept editor configuration files out of this repo in order to
keep it as simple and environment agnostic as possible. However, we recommend
using the following settings:

* indent using spaces
* set tab width to 2 spaces (keeps the matrices in source code aligned)

## Generating Additional Data

This is optional!

If you'd like to generate your own radar and lidar data, see the
[utilities repo](https://github.com/udacity/CarND-Mercedes-SF-Utilities) for
Matlab scripts that can generate additional data.
