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
    - [Project organization and stakeholders](project-organization-and-stakeholders)
    - [Project’s budget and schedule](project’s-budget-and-schedule)
    - [Risks of the project and preconditions for the success of the project](risks-of-the-project-and-preconditions-for-the-success-of-the-project)
2. [The working plan](the-working-plan)
    - [Phasing and timing of the work](phasing-and-timing-of-the-work)
    - [Project management](project-management)
    - [Methods used in the thesis project](methods-used-in-the-thesis-project)

&nbsp;[Appendix 1 Pictures of the project’s current state](appendix-1-pictures-of-the-project’s-current-state)  
&nbsp;[Appendix 2 Phasing and timing of the project](appendix-2-phasing-and-timing-of-the-project)
    
## Project definition

### The background of the project

The goal of this thesis is to create a fully functional home automation and security sys-tem.

The subject of home automation has been talked about over the past years, but some-times these systems are not as useful as they are supposed to be. For example, is not it easier to switch on or off the coffee machine or light the traditional way than to use a smartphone or browser to do these simple tasks.

In the bachelor thesis, the solution to the mentioned problem and similar ones will be suggested and in order to do so the system will be tested based on the real life scenarios.

There are home automation products available off-the-shelf. The problem is that they are expensive and sometimes do not offer a solution to some personal needs.

A prototype for the project has been already created. Currently, the system is able to turn on/off a PC remotely or trough voice control. The system is also able to control several other electronic devices. There are some issues with the security system which are planned to be fixed. The system has a graphical user interface that is currently working with some minor problems.

Testing and some additional research is required in order to improve the final results and make a full demonstration of how the system performs.

### Potential sources

The following book offers useful information that can be used for the project's imple-mentation. The book explains how Python can be used to work with GPIOs and it can be useful for this project.
* Getting Started with Raspberry Pi (By Matt Richardson and Shawn Wallace)

The other book that can be used is covering some basics and instructions of working with the Apache server which are useful to design a Web-UI. This thesis is not covering basics in depth, but some basic knowledge will be required.
* Learn Raspberry Pi with Linux (By Peter Membrey , David Hows)

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

This project is set to create a fully modified and personalized home automation and se-curity system with the Raspberry Pi, some additional sensors and external devices. 

Some pictures from the current state of the project are attached at the end of this doc-ument ([Appendix 1](#appendix-1-pictures-of-the-project’s-current-state)).

### Objectives and deliverables of the project

The home automation and security system that set to be created will have the following functionalities.

Home automation:
* Ability to switch on/off some home devices
* The system can measure home and outside temperature
* System will be able to control home devices based on the home temperature
* The home automation system will be able to set time for turning on/off home devices.

Security system:
* The system will trigger an alarm in the case of home intrusion
* The system also will capture a short video clip of the incident
* The security system will upload the video to an online server
* It must be able to send notifications to the homeowner via SMS and e-mail
* In case of emergency if someone is home alone, there will be a panic button which can be utilized to notify other residents

Finally, a web-server and PHP server will be implemented to serve for the graphical user interphase of the project.

The purpose of this thesis is to examine different ways of using the Raspberry Pi as a multifunctional device in particular as a basic home automation and security system. An-swering to the following questions will help to reach goals of this bachelor thesis:
* What are the possibilities to create a programmable home automation and securi-ty system using the Pi?
    - Will such a system provide expected functionalities which are mentioned above in the subchapter 1.4?
    - What is the money cost for completing the project?
