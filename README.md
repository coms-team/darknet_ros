# YOLO ROS: Real-Time Object Detection for ROS

## Overview

This is a ROS package developed for object detection in camera images. You only look once (YOLO) is a state-of-the-art, real-time object detection system. In the following ROS package you are able to use YOLO on GPU and CPU. The pre-trained model of the convolutional neural network is able to detect aeroplane, bicycle, bird, boat, bottle, bus, car, cat, chair, cow, dining table, dog, horse, motorbike, person, potted plant, sheep, sofa, train and tv monitor. For more information about YOLO, Darknet, available training data and training YOLO see the following link: [YOLO: Real-Time Object Detection](http://pjreddie.com/darknet/yolo/).

The YOLO packages have been tested under ROS Indigo and Ubuntu 14.04. This is research code, expect that it changes often and any fitness for a particular purpose is disclaimed.

**Author: Marko Bjelonic, marko.bjelonic@mavt.ethz.ch**

**Affiliation: Robotic Systems Lab, ETH Zurich**


## Citing

The YOLO methods used in this software are described in the paper: [You Only Look Once: Unified, Real-Time Object Detection](https://arxiv.org/abs/1506.02640).

## Installation

### Dependencies

This software is built on the Robotic Operating System ([ROS]), which needs to be [installed](http://wiki.ros.org) first. Additionally, YOLO for ROS depends on following software:

- [Darknet](https://github.com/pjreddie/darknet) (open source neural network framework written in C and CUDA)
- [OpenCV](http://opencv.org/) (computer vision library),
- [boost](http://www.boost.org/) (c++ library),

### Building

In order to install darknet_ros, clone the latest version from this repository into your catkin workspace and compile the package using ROS.

    cd catkin_workspace/src
    git clone --recursive git@bitbucket.org:leggedrobotics/darknet_ros.git
    cd ../
    catkin build darknet_ros

### Download weights

The yolo-voc.weights and tiny-yolo-voc.weights are downloaded automatically in the CMakeLists.txt file. If you need to download them again, go into the weights folder and download the two pre-trained weights

    cd catkin_workspace/src/darknet_ros/darknet_ros/weights/
    wget http://pjreddie.com/media/files/yolo-voc.weights
    wget http://pjreddie.com/media/files/tiny-yolo-voc.weights

### Unit Tests

Run the unit tests with

    catkin build darknet_ros --no-deps --verbose --catkin-make-args run_tests

You will see the following two figures popping up :

![Darknet Ros example: Detection image 1](darknet_ros/doc/dog.png)
![Darknet Ros example: Detection image 2](darknet_ros/doc/person.png)
