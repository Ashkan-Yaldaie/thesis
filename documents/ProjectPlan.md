# Home automation and security system with the Raspberry Pi

Ashkan Yaldaie

Project plan  
Thesis  
14 October 2015

## Table of contents
1.  [Project definition](#project-definition)
    - [The background of the project](#the-background-of-the-project)
    - [Potential sources](#potential-sources)
    - [Work statement](#work-statement)
    - [Objectives and deliverables of the project](#objectives-and-deliverables-of-the-project)
    - [Out of scope](#out-of-scope)
    - [Project organization and stakeholders](#project-organization-and-stakeholders)
    - [Project’s budget and schedule](#projects-budget-and-schedule)
    - [Risks of the project and preconditions for the success of the project](#risks-of-the-project-and-preconditions-for-the-success-of-the-project)
2. [The working plan](#the-working-plan)
    - [Phasing and timing of the work](#phasing-and-timing-of-the-work)
    - [Project management](#project-management)
    - [Methods used in the thesis project](#methods-used-in-the-thesis-project)

&nbsp;[Appendix 1 Pictures of the project’s current state](#appendix-1-pictures-of-the-projects-current-state)  
&nbsp;[Appendix 2 Phasing and timing of the project](#appendix-2-phasing-and-timing-of-the-project)
    
## Project definition

### The background of the project

The goal of this thesis is to create a fully functional home automation and security system.

The subject of home automation has been talked about over the past years, but sometimes these systems are not as useful as they are supposed to be. For example, is not it easier to switch on or off the coffee machine or light the traditional way than to use a smartphone or browser to do these simple tasks.

In the bachelor thesis, the solution to the mentioned problem and similar ones will be suggested and in order to do so the system will be tested based on the real life scenarios.

There are home automation products available off-the-shelf. The problem is that they are expensive and sometimes do not offer a solution to some personal needs.

A prototype for the project has been already created. Currently, the system is able to turn on/off a PC remotely or trough voice control. The system is also able to control several other electronic devices. There are some issues with the security system which are planned to be fixed. The system has a graphical user interface that is currently working with some minor problems.

Testing and some additional research is required in order to improve the final results and make a full demonstration of how the system performs.

### Potential sources

The following book offers useful information that can be used for the project's implementation. The book explains how Python can be used to work with GPIOs and it can be useful for this project.
* Getting Started with Raspberry Pi (By Matt Richardson and Shawn Wallace)

The other book that can be used is covering some basics and instructions of working with the Apache server which are useful to design a Web-UI. This thesis is not covering basics in depth, but some basic knowledge will be required.
* Learn Raspberry Pi with Linux (By Peter Membrey, David Hows)

Vesa-Matti Yli-Heikkilä has created a basic home surveillance system. His work can be a starting point.
* Home surveillance with Raspberry Pi (Bachelor thesis by Vesa-Matti Yli-Heikkilä)

Some online instructions will also be included as sources for this paper.
* Raspberry Pi Foundation URL: https://www.raspberrypi.org/
* Raspberry Pi Spy URL: http://www.raspberrypi-spy.co.uk/
* ModMyPi URL: http://www.modmypi.com/
* The Pi Hut URL: http://thepihut.com/
* Tero Karvinen URL: http://terokarvinen.com/

Additional resources will be used for this project, so the complete list of sources will be provided in the final paper. 

### Work statement

This project is set to create a fully modified and personalized home automation and security system with the Raspberry Pi, some additional sensors and external devices. 

Some pictures from the current state of the project are attached at the end of this document ([Appendix 1](#appendix-1-pictures-of-the-projects-current-state)).

### Objectives and deliverables of the project

The home automation and security system that set to be created will have the following functionalities.

Home automation:
* Ability to switch on/off some home devices
* The system can measure home temperature
* System will be able to control home devices based on the home temperature
* The home automation system will be able to set time for turning on/off home devices.

Security system:
* The system will trigger an alarm in the case of home intrusion
* The system also will capture a short video clip of the incident
* The security system will upload the video to an online server
* It must be able to send notifications to the homeowner via SMS and e-mail
* In case of emergency if someone is home alone, there will be a panic button which can be utilized to notify other residents

Finally, a web-server and PHP server will be implemented to serve for the graphical user interface of the project.

The purpose of this thesis is to examine different ways of using the Raspberry Pi as a multifunctional device in particular as a basic home automation and security system. Answering to the following questions will help to reach goals of this bachelor thesis:
* What are the possibilities to create a programmable home automation and security system using the Pi?
    - Will such a system provide expected functionalities which are mentioned [above](#objectives-and-deliverables-of-the-project)?
    - What is the money cost for completing the project?

### Out of scope

Basics will be covered very briefly in the final paper such as Linux installation and configuration for the Raspberry Pi.
At this stage, this project is for a personal home usage, so such functionalities that are more useful for a firm will be excluded from this thesis work. An online video streaming of the area can be mentioned as an excluded functionality.

### Project organization and stakeholders

School’s advisor of the thesis: Tero Karvinen

Since at this stage the project is for home usage, the potential target group includes home and small business owners.

### Project’s budget and schedule

Any instruction available in books and web articles contain a list of hardware. In order to complete the project, the available hardware to the developer will be used. Purchase of any extra devices will be avoided if it is not really necessarily. However, a list of used devices for this project will be provided to calculate the budget.

The starting date and the ending date of the project are: 1 October 2015 – 29 February 2016.

### Risks of the project and preconditions for the success of the project
One of the purposes of this project is to control home devices and since they work with high voltage from 100v to 240v, it is required to be an electrician to deal with high current. Due to this, radio remote control sockets will be used for this project.

Buying sensors from the local shops will be avoided due to the high prices. Sensors and additional devices will be bought mostly from China. The internet shop “ebay.com” will be used to make purchases.

The only obstacles to be faced if goods are bought from China are a long waiting period and lack of quality. However, to avoid such problems items will be bought from known sellers and will be ordered beforehand.

## The working plan

### Phasing and timing of the work
After studying the goals of the project, the work will continue by creating a list of devices that need to be bought.

The next stage will be studying about the safety measures of working with high current and start configuring the Raspberry Pi and its operating system. A list of software will be created to be installed on the Raspberry Pi.

Working and testing external devices is the next stage. Writing and modifying some codes is also required to personalize some functionalities.

Finally, a graphical user interface will be created and the project will be tested using the real life scenarios over some period of time.

The phasing is presented in more details in [Appendix 2](#appendix-2-phasing-and-timing-of-the-project).

### Project management

All the decisions which are related to the thesis project, including the acceptance of results, are made in a steering group. After starting the meeting, the date and place of the next steering group meeting is agreed on at the previous meeting. The project manager sends the material which is dealt with in the meeting to the members of the steering group three weekdays before the meeting. A notice of a meeting is sent to all the meetings. The material of the beginning meeting is a project plan, the material of control meetings is a status report and the results that have been shown in the project plan are delivered to the final meeting. If the project cannot be promoted, for one reason or another, according to the one that has been designed in the project plan, the project manager convenes an extraordinary steering meeting and proposes the amendment drawn up by it. It contains the proposal for the updated project plan. The steering group decides about the changes. After the steering meetings, the project manager will deliver minutes within three weekdays from the meeting to the steering group. The project manager will be responsible for the communication between the separate parties, in other words, the interest groups of the project for the work, if anything else is not decided in the steering meeting.

### Methods used in the thesis project
In order to complete the paper, a working system must be implemented. To test the system, real-life situations and scenarios will be created and tested. The information will be collected from the books and instructions, of course, some things must be modified to be compatible with the available hardware and personal needs.
The methods are the implementation of the system, testing the project and reporting the results.

## Appendix 1 Pictures of the project’s current state

<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/cables.jpg" width="300" height="225">
<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/gpios.jpg" width="300" height="225">

<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/relays.jpg" width="300" height="225">
<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/usb-ports.jpg" width="300" height="225">

<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/userinterface.png" width="200" height="491">

## Appendix 2 Phasing and timing of the project

|Milestone|Week number|Deliverable|
| --- | --- | --- |
|Preparation for the first meeting|40|Topic proposal and topic paper|
|First meeting and working on the project plan|41|First version of the project plan|
|Second meeting and completing the project plan|42|Plan for the full thesis project|
|Completing the table of contents|43|Table of contents|
|Working on the prototype issues|44|Radio frequency sockets working|
|Completing the development phase|45-46|Required features of the system|
|Testing and fixing all possible issues|47-48|A system without visible errors|
|Having a control meeting|49|Half of the paper|
|Continuing to write the final paper|50|70% of the paper completed|
|Completing the seminar presentation|51|Seminar presentation|
|Having a control meeting|52|Chapter four is finished|
|Working on the paper’s remaining issues|53-1|90% of the paper|
|Discussion with the thesis advisor|2|Corrected version of the paper|
|Completing and preparing the paper|3-5|99% of the thesis paper|
