---
layout: post
title:  "What is AWI?"
date:   2022-02-23 19:35:45 -0400
categories: AWI
image: "AWILOGO.png"
---


<h3> What is AWI? </h3>


The Astronaut Wrist Interface (AWI) has been a project that I have been working on as my senior design project. What started as a simple school assignment quickly turned into a project that I fell in love with. The first and most important reason why this project has been a delight is because of its balance between complexity and feasibility. The development of the AWI is by no means an easy task, but because of the scale of the project I have had the privilege of developing a prototype of the flight unit device. For a while I debated to myself about making this post or series of posts about the project, but it has been such a cool project that I felt compelled to share it. Before going any further on my journey with AWI, what even is AWI?

The Astronaut Wrist Interface (AWI) in its most stripped down version would be an interactive device located on the wrist/cuff of an astronaut's extra-vehicular activity suit (EVA suit) that provides him or her with an interface that displays mission checklists, suit telemetry data, and a navigation system. The long term vision for the AWI system is an interactive platform that could allow astronauts to also control robots or other space machines, connect and interact with a heads-up display, and more. The system would help astronauts perform missions outside spacecraft, or planetary bases. 


<h3> Why hasn't something like the AWI been developed already? </h3>


The truth is that a system like the AWI has already been developed and tested by NASA in the 90s. NASA developed an electronic checklist that also went on the cuff of the EVA suit. This electronic checklist was tested on several missions in the Shuttle era. Some of the most critical feedback from the mission tests included battery or display failures due to extreme temperatures of space, while some of the less critical but still noteworthy feedback notes related to the glare of the screen, or the bulkiness of the overall device (Marmolejo). The image below shows the electronic cuff developed by NASA. Some of the important features of the NASA's electronic cuff were an LCD screen, LCD heater, and a Lithium-Bromide battery pack.  
 
The NASA electronic cuff's development was stagnated in a sense due to the technology available at the time. Thankfully, nowadays, the smartphone industry as well as the battery industry are leaps ahead in technology to what was available during that time. New types of display technologies like flexible OLED screens allow for better resolution in a less bulky package. New Lithium-ion batteries are allowing high power consumption devices to be on for extended periods of time, while taking up less space.

While the technology in almost every component of the electronic cuff has been improved, the harsh environment of space still poses a very tough challenge. The current battery and display technology is still not advanced enough to withstand the extreme temperatures of space. Any system developed right now would still need to deal with heaters and proper thermal balances for the components. By far, the greatest improvement in today's technology compared to the technology of the time, is the reliability of the display and battery systems.

I believe that with the current technology a system like the AWI would be difficult to develop, but feasible. At the end of the day, it being difficult to develop is what makes it fun. 

<figure align="center">
    <img src='/postImages/AWI/electronicCuff.png' alt='missing' />
    <figcaption> NASA Electronic Cuff (Photo Credit: NASA, Marmolejo) </figcaption>
</figure>

---

### *Mark I* prototype general information
These are some of the main components I utilized to develop the first prototype (*Mark I*)
- Raspberry Pi 4 
- Arduino nano
- Kuman 7 in touchscreen display
- HiLetgo 433 MHz transmitter and receiver  
- DS18B20 Temperature sensor module
- Adafruit 9-DOF IMU Fusion-Breakout BNO055
- 7 Push buttons

#### Main features of AWI prototype/concept
As mentioned above, in its most stripped down version, the AWI system would provide mission checklists, suit telemetry data, and a navigation system. In this specific post, I will focus on the overall features and solutions that the current AWI prototype has and how it compares to previous NASA solutions. In future posts, I am planning on delving more into some of the specifics regarding the program's design and technologies, as well as some of the physical design features. 

---
### Specific Subsystems

#### Checklists
Just like the NASA electronic cuff, the AWI system displays mission instructions and checklists that astronauts need during EVA operations. One of the advantages brought by the technology from today is the implementation of images or videos on the checklists that can help the astronaut complete complex tasks. The other important improvement from the AWI when compared to the previous checklist systems is the ability to wirelessly modify or update any instructions without having to open the device's enclosure. It is worth to note that previous to the NASA electronic cuff system, astronauts relied on little notebooks on their cuffs. These notebooks held a very limited amount of information and were cumbersome to use. Previous to a mission, the astronauts would add the mission specific checklists, as well as some drawings. 

<figure align="center">
    <img src='/postImages/AWI/oldChecklist.png' alt='missing' />
    <figcaption> Cuff Checklist, EVA 2 & 3, Apollo 16 (Young, John), National Air and Space Museum </figcaption>
</figure>


#### Telemetry
As can be seen in the diagram above, the telemetry dashboard is divided into two main information panels. The telemetry data from the astronaut suit. This dashboard displays the vitals of the person, as well as suit data like: pressure, power, and temperature. The AWI system picks up the suit's information from an S-band transmission from the suit itself, processes it and displays it in an easy and quick to read dashboard. On top of the dashboard, the AWI system has an alert system for warnings and emergencies. 

Previous to the AWI system, astronauts would have a mirror on their cuff that would allow them to see some telemetry data as well as having a rudamentary way of controlling some features of the suit. During the Apollo period, this panel was called the Remote Control Unit (RCU), today it is the Display and Control Module (DCM). Both of these systems can be seen below. 

<figure align="center">
    <img src='/postImages/AWI/RCU.jpg' alt='missing' />
    <figcaption> Apollo Remote Control Unit (RCU) for the Portable Life Support System (PLSS) and Extravehicular Mobility Unit (EMU) (Karl Dodenhoff)</figcaption>
</figure>

<figure align="center">
    <img src='/postImages/AWI/DCU.jpg' alt='missing' />
    <figcaption> Break down of DCU system (NASA, US SpaceGear) </figcaption>
</figure>


#### Navigation
The last main system that the Mark I version of the AWI currently has is a navigation system. Unfortunately, having a navigation system on the AWI system is not as easy as setting up a GPS module. This is due to the lack of orbiting satellites on celestial bodies like the moon or Mars, where the upcoming EVA missions are expected to take place. Having a navigation system during an EVA assignment is crucial, given that the uniformity of the terrain can be very disorienting for the astronauts. 

The AWI combines two different types of navigation modules that together improve accuracy, and add another layer of redundancy in the event one of the module fails. The first method of navigation is a radio direction finding system. The second module is an inertial navigation unit. In the next part of this blog post, I will go over how these modules work individually. 
