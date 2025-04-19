Dune WRO Future Engineers team
====
This repository contains engineering materials of a self-driving and lego-made vehicle's model participating in the WRO Future Engineers competition in the season 2025.
Instagram: @dunewro
Youtube: Dune (@Dune-sa) 
or URL Link: https://www.youtube.com/@Dune-sa

![image alt](https://github.com/duneteam1/wro2024futureengineersduneteam/blob/main/channels4_banner.jpg?raw=true)
## Content

* `t-photos` contains 2 photos of the team (an official one and one funny photo with all team members)
* `v-photos` contains 6 photos of the vehicle (from every side, from top and bottom)
* `video` contains the video.md file with the link to a video where driving demonstration exists
* `schemes` contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
* `src` contains code of control software for all components which were programmed to participate in the competition
* `models` is for the files for models used by 3D printers and key-custom details of our vehicle. There is how we combined the lego and Raspberry Pi 4 Build hat.
* `other` is for other files where you can understand how to prepare the vehicle for the competition. It includes documentation about datasets, hardware specifications, communication protocols descriptions etc. In addition, there are some photos of our process.

## Introduction

Welcome to the repository of Team Dune for the World Robotic Olympiad competition! In this README, we will provide an overview of our robot design, including its electromechanical components, code structure, and the process to build, compile, and upload the code to the vehicle's controllers.

Sagy - Captain, Coder.
Alikhan - responsible for GitHub and engineering journal, Robotics Engineer.
Johnny - our car.

## A short description of how we made a self-driving vehicle
We have built a vehicle from Lego Spike Prime kit combining it with Raspberry Pi 4 build hat and raspberry Pi camera v2.1.
Our electronics consists of a Raspberry Pi Camera v2.1 and Raspberry Pi 4 build hat, 1 Ultrasonic Sensor, 2 Big motor drivers, 1 colour sensor from Lego Spike Prime kit. In order for him to drive in an empty field, we made an algorithm where ultrasonic sensor evaluates the distance from the right side and keep the vehicle in the cente, then when the colour sensor detects the color (yellow or blue) on the field, it turns whether to the right or left.
For object recognition, we use Raspberry Pi camera v2.1. When the camera sees an obstacle, it returns for built hat the ID of the object and its height. Red objects have an ID of 1 and green ones have an ID of 2. performing a detour around the object, the object itself must have a height of more than 100 pixels so that those objects that are behind the right one are not recorded in the variable. That is, to perform a detour, two conditions must be met: the color of the object and its height must be more than 100 pixels.The servo motor is connected to the wheels using a steering rack and the draviver motor gives additional voltage to the motor because the arduino does not give full voltage to the motor.We made algorithms that did it all.

## Conclusion
As a result, we wrote the code and created a robot so that it could drive itself, that is, autonomously.With the help of ordinary things, we made an autonomous car.We are glad that you can now also replicate such an autonomous machine for yourself by watching and copying the code in our GitHub.We have also added comments and explanations everywhere to make it easier for you to understand all this.Also, do not repeat our mistakes and do what you want.We believe in you!
