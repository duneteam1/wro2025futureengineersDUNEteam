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
-  1 motor driver L298N
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

We are participating since the previous year and we are diving in this season with some experience. **In the previous 2024 season**, we lost the game because our vehicle's electronics was confused and eventually burnt.This year we had to fix this problem and do not repeat it in this season. Therefore,we started making robot from Lego Prime kit,by believieng that electronic's easy functionability will change everything. We have been coding our vehicle for a months,but couldnt automize it. So thats why we returned to our old vehicle before 1 day of competition. **This challenge was the main one** and we experienced a lot of stress and exhaustion because of it. Because we wanted to both meet the deadlines and make our vehicle powerful. Now, we changed the servo motor and used Raspberry Pi pico 4 instead of Arduino. It is mor comfortable and understandable, because arduino recquired a lot of wires that hampered to the whole system. 

## Teamwork
Our team consisted of three members: Alikhan, Sagy and Johny(our vehicle).
We are used to be classmates. In addition,we have a good contact and have succesfully worked in the team and helped each other. Both of us played the crucial roles in this project. My role is main engineer while Sagy is coder. Furthermore, we have had a huge experience in the First Tech Challenge, and we were doing great with the vehicle.

## CHALLENGES
To be honest, we have gone through many challenges that have been killing us inside out.We had the problem with servo and wires,in which we evetually changed everything and made wires more thickier.
Our robot had undergone many changes and even was replaced 1 day before the competetion. We have been building vehicle from details of Lego Prime kit,but it was hard to connect it with electronics in the end.So we decided to go back to the old vehicle and enhance it. We changed our vehicle in just one night. You can see changes of vehhicle in "others"

## Conclusion
As a result, we wrote the code and created a robot so that it could drive itself, that is, autonomously.With the help of ordinary things, we made an autonomous car.We are glad that you can now also replicate such an autonomous machine for yourself by watching and copying the code in our GitHub.We have also added comments and explanations everywhere to make it easier for you to understand all this.Also, do not repeat our mistakes and do what you want.We believe in you!

## Special thanks
Special thanks to our coach,Yerzhan Auyezov and Alikhan Essally from the [Quantum STEM School](https://quantum.edu.kz/en/)) for helping us to build, programm our  vehicle and co-ordinate us throughout the preparation.Our school, **Quantum STEM shool** provived us the space to prepare to the competition.In addition, this school made a huge impact on our vehicle by supporting it in financially win. **We very appreciate it!** 🙂.
