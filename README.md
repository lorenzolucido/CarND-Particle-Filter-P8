# **Kidnapped Vehicle Project: Particle Filter**
#### _Lorenzo's version_
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

[results]: ./result.png

## Project Introduction
In this project I implemented a 2 dimensional particle filter for a self-driving car in C++. It is given a map and some initial localization information (analogous to what a GPS would provide). At each time step the filter will gets observation and control data.

## Implementation
The key part of the code is located in `src/particle_filter.cpp`.

- `ParticleFilter::init` initializes the 20 particles randomly around the GPS initial (inaccurate) observation.
- `ParticleFilter::prediction` moves all the particles according to the control data velocity and yaw rate, and takes into account the error linked to controls
- `ParticleFilter::updateWeights` computes and normalizes the weight of each particle, given how likely a particle is to be close to the actual location, given the observations (matched with the closest landmark)
- `ParticleFilter::resample` draws randomly a new set of particles proportionally to the weights computed in `updateWeights`

## Results
See image below:
![alt text][results]

## Running the Code
This project involves the Term 2 Simulator which can be downloaded [here](https://github.com/udacity/self-driving-car-sim/releases)

This repository includes two files that can be used to set up and intall uWebSocketIO for either Linux or Mac systems. For windows you can use either Docker, VMware, or even Windows 10 Bash on Ubuntu to install uWebSocketIO.

Once the install for uWebSocketIO is complete, the main program can be built and ran by doing the following from the project top directory.

1. mkdir build
2. cd build
3. cmake ..
4. make
5. ./particle_filter

Alternatively some scripts have been included to streamline this process, these can be leveraged by executing the following in the top directory of the project:

1. ./clean.sh
2. ./build.sh
3. ./run.sh
