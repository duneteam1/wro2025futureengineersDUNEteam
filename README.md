Engineering materials
====

This repository contains engineering materials of a self-driving vehicle's model participating in the WRO Future Engineers competition in the season 2024.

## Content

* `t-photos` contains 2 photos of the team (an official one and one funny photo with all team members)
* `v-photos` contains 6 photos of the vehicle (from every side, from top and bottom)
* `video` contains the video.md file with the link to a video where driving demonstration exists
* `schemes` contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
* `src` contains code of control software for all components which were programmed to participate in the competition
* `models` is for the files for models used by 3D printers, laser cutting machines and CNC machines to produce the vehicle elements. If there is nothing to add to this location, the directory can be removed.
* `other` is for other files which can be used to understand how to prepare the vehicle for the competition. It may include documentation how to connect to a SBC/SBM and upload files there, datasets, hardware specifications, communication protocols descriptions etc. If there is nothing to add to this location, the directory can be removed.

## Introduction

Welcome to the repository of Team Dune for the World Robotic Olympiad competition! In this README, we will provide an overview of our robot design, including its electromechanical components, code structure, and the process to build, compile, and upload the code to the vehicle's controllers.

Sagy - Captain, Coder.
Alikhan - responsible for GitHub and engineering journal, Engineer.
Johnny - our car.

## A short description of how we made a self-driving vehicle
Our electronics consists of a HuskyLens camera, 4 HC SR04 Ultrasonic Sensors,Arduino Nano,Motor Driver,MG996R Servo Motor,DC Motor.In order for him to drive in an empty field, we made an algorithm that compares distances from the sides and turns in the right direction.
And for object recognition, we use HuskyLens.And when the husky sees an object, it returns for arduino the ID of the object and its height. Red objects have an ID of 1 and green ones have an ID of 2. performing a detour around the object, the object itself must have a height of more than 100 pixels so that those objects that are behind the right one are not recorded in the variable. That is, to perform a detour, two conditions must be met: the color of the object and its height must be more than 100 pixels.The servo motor is connected to the wheels using a steering rack and the draviver motor gives additional voltage to the motor because the arduino does not give full voltage to the motor.We made algorithms that did it all.

First algoritm:
Second algoritm:

## Conclusion
As a result, we wrote the code and created a robot so that it could drive itself, that is, autonomously.With the help of ordinary things, we made an autonomous car.We are glad that you can now also replicate such an autonomous machine for yourself by watching and copying the code in our GitHub.We have also added comments and explanations everywhere to make it easier for you to understand all this.Also, do not repeat our mistakes and do what you want.We believe in you!
