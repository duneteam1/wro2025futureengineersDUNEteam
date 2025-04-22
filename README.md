Dune WRO Future Engineers team
====
This repository contains engineering materials of a self-driving vehicle's model participating in the WRO Future Engineers competition in the season 2025.
Made by the team Dune founded in Quantum STEM School, Astana.

![image alt](https://github.com/duneteam1/wro2024futureengineersduneteam/blob/main/channels4_banner.jpg?raw=true)
## Content

* `t-photos` contains 2 photos of the team (an official one and one funny photo with all team members)
* `v-photos` contains 6 photos of the vehicle (from every side, from top and bottom)
* `video` contains the video.md file with the link to a video where driving demonstration exists
* `schemes` contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
* `src` contains code of control software for all components which were programmed to participate in the competition
* `models` is for the files for models used by 3D printers and key-custom details of our vehicle. There is how we combined the kit and Raspberry Pi 4 Build hat.
* `other` is for other files where you can understand how to prepare the vehicle for the competition. It includes documentation about datasets, hardware specifications, communication protocols descriptions etc. In addition, there are some photos of our process.

## Introduction

Welcome to the repository of Team Dune for the World Robotic Olympiad competition! In this README, we will provide an overview of our robot design, including its electromechanical components, code structure, and the process to build, compile, and upload the code to the vehicle's controllers.


## A short description of how we made a self-driving vehicle
We have built a vehicle from a ordinary kit combining it with Raspberry Pi 4 and raspberry Pi camera v2.1.
**Our electronics consists of**
- a Raspberry Pi Camera v2.1 and Raspberry Pi4
-  2 light distance Sensor
-  1 Big motor driver
-  1 REV servo motor
-  1 powerbank
-  1 battery folder
-  1 motor driver.
  In order for him to drive in an empty field, we made an algorithm where 2 distance sensors evaluates the distance from the both side and keep the vehicle in the centre. To make vehicle turn whether right or left, it works with proporion of both distances and compares it.
**Formula:**
a = 400

b = 390
if a > b:
    kef = b / a * 30 - 30
    print(1)
else:
    kef = round(-1* (a / b * 30 - 30))
    print(2)

print(kef)

**For object recognition**, we use Raspberry Pi camera v2.1. When the camera sees an obstacle, it creates the mask in the zone of colors.Then, if it detects the object succesfully, it calculates the area ob object and compares it to need area. Algorithm fins the object in zone of The servo motor is connected to the wheels using a steering rack and the draviver motor gives additional voltage to the motor because the arduino does not give full voltage to the motor.We made algorithms that did it all.If the algorithm finds two colors in its ranges and if such a color was found, then the mask is addressed and the object is found. And if from those objects those are selected whose area corresponds to the specified parameter, the algorithm returns the largest area of ​​the object and goes around it with the code in src.


# Our journey

  Our challenges and successes during the few months of preparation are detailed in this text.  We had to redo a lot of things and figure out a lot of things to get our robot to function.
  
>Members

 **Sagy Token** - Captain, Coder.
 **Alikhan Tolegenov** - incharge of GitHub, Robotics Engineer.
 **Johny** - our vehicle.

>Coach

**Yerzhan Auyezov** - our mentor and coach from Quantum STEM School.
 
- **YouTube**: [https://www.youtube.com/channel/UCyzm_Su7qoRCof-ZpbG_9Ig](https://www.youtube.com/@Dune-sa)
  - Here you can watch videos about past competitions and current preparation.
- **Instagram**: [@dunewro](https://www.instagram.com/dunewro/)
  - Cool posts and updates about our.
We are participating since the previous year and we are diving in this season with some experience. In the previous 2024 season, we lost the game because our vehicle's 


## Conclusion
As a result, we wrote the code and created a robot so that it could drive itself, that is, autonomously.With the help of ordinary things, we made an autonomous car.We are glad that you can now also replicate such an autonomous machine for yourself by watching and copying the code in our GitHub.We have also added comments and explanations everywhere to make it easier for you to understand all this.Also, do not repeat our mistakes and do what you want.We believe in you!
