<p align="right">
<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/haaga-helia.png">
</p>

# Home automation and security system with the Raspberry Pi

Ashkan Yaldaie

Bachelor Thesis  
HAAGA-HELIA University of Applied Sciences  
8 November 2015

## Table of contents
&nbsp;[Tables and Figures](#tables-and-figures)  
&nbsp;[Abbreviations and terms](#abbreviations-and-terms)

1. [Introduction](#introduction)
  - [Project questions and objectives](#project-questions-and-objectives)
  - [Project's purpose and scope](#projects-purpose-and-scope)
  - [Methodology](#methodology)
2. [Background](#background)
  - [Why Raspberry Pi?](#why-raspberry-pi)
  - [Home automation and security system](#home-automation-and-security-system)
3. [Implementation of a home automation and security system](#implementation-of-a-home-automation-and-security-system)
  - [List of required sensors and devices](#list-of-required-sensors-and-devices)
  - [Setting up the Raspberry Pi](#setting-up-the-raspberry-pi)
  - [Home automation](#home-automation)
    - [WIFI sockets](#wifi-sockets)
    - [Radio frequency sockets](#radio-frequency-sockets)
    - [Control a socket using home temperature](#control-a-socket-using-home-temperature)
    - [Control a socket using timer](#control-a-socket-using-timer)
    - [Voice control](#voice-control)
  - [Security system](#security-system)
    - [Adding a wireless motion sensor](#adding-a-wireless-motion-sensor)
    - [Sending SMS and triggering an alarm if motion is detected](#sending-sms-and-triggering-an-alarm-if-motion-is-detected)
    - [Implementation of a panic button](#implementation-of-a-panic-button)
    - [Connecting a camera to the system](#connecting-a-camera-to-the-system)
    - [Capturing a video clip of an intrusion](#capturing-a-video-clip-of-an-intrusion)
    - [Uploading the video to the cloud and sending an email notification](#uploading-the-video-to-the-cloud-and-sending-an-email-notification)
    - [Controlling the security system via Bluetooth](#controlling-the-security-system-via-bluetooth)
  - [Creating a graphical user interface for the system](#creating-a-graphical-user-interface-for-the-system)
4. [Testing](#testing)
5. [Ways to improve future implementations](#ways-to-improve-future-implementations)
6. [Conclusion](#conclusion)

&nbsp;[References](#references)  
&nbsp;[Appendix](#appendix)

## Tables and Figures

[Figure 1](#figure-1): The Raspberry Pi and its connectors

&nbsp;[Table 1](#table-1): Raspberry Pi 2 vs Beaglebone hardware chart

## Abbreviations and terms

<table>
  <tbody>
    <tr>
      <td>DIY</td>
      <td>Do It Yourself</td>
    </tr>
    <tr>
      <td>GPIO</td>
      <td>General Purpose Input/Output</td>
    </tr>
    <tr>
      <td>HDMI</td>
      <td>High-Definition Multimedia Interface</td>
    </tr>
    <tr>
      <td>MicroSD</td>
      <td>Micro Secure Digital</td>
    </tr>
    <tr>
      <td>PC</td>
      <td>Personal Computer</td>
    </tr>
    <tr>
    <tr>
      <td>RAM</td>
      <td>Random Access Memory</td>
    </tr>
      <td>RasPi</td>
      <td>Raspberry Pi is a single-board computer</td>
    </tr>
    <tr>
      <td>SMS</td>
      <td>Short Message Service</td>
    </tr>
    <tr>
      <td>USB</td>
      <td>Universal Serial Bus</td>
    </tr>
  </tbody>
</table>

## Introduction

Smart homes are gaining in popularity. Nowadays people prefer to automate the common everyday tasks to make the life more comfortable. Moreover, many people are thinking about the security of their houses and choose to acquire a system that can protect their dwellings. There is a wide choice of home automation and security systems which can match with any budget. However, more or less functional ones are rather expensive and not necessarily meet all the needs of a customer. What is more, such systems are usually rented to a customer for a monthly fee but as soon as the client decides to stop using the system, it will be taken away by the company. And since most of the well-functional systems cost a lot, cheaper examples which could compete with them are in demand, that is why there is a room for the system represented in the thesis.

The system in question is going to be more affordable than other similar ones, however, it will give the user the opportunity to combine both a home automation and security system. The system is build using a Raspberry Pi and the paper gives the understanding of how useful it can be.

The market of home automation is rather new and there is a great room for development. There was a shifting from carrying out quite basic tasks to more complicated ones. Nowadays nobody is going to be surprised by switching off light with clapping or automatically running water from the tap when hands are placed under it, but still there are so many other things which can be done.

No doubt, that building of such complicated things like a smart cooker or a robot that can feed your pet requires funding to be created, but most of the people would be happy to have at least basic features available at the affordable price.

### Project questions and objectives

The paper's objectives are to check what kind of functions the Raspberry Pi can offer in relation to the building of a home automation and security system and what are its benefits.  Answering to the following questions will help to understand how wide the scope is when working with this tiny computer:

- What are the possibilities to create a programmable home automation and security system by using the RasPi?
 - What is the money cost for completing the project?
 - Will such a system provide expected functionalities which are listed below?

Home automation:

- Ability to switch on/off some home devices
- The system can measure home temperature
- System will be able to control home devices based on the home temperature
- The home automation system will be able to set time for turning on/off home devices.

Security system:

- The system will trigger an alarm in the case of home intrusion
- The system also will capture a short video clip of the incident
- The security system will upload the video to an online server
- It must be able to send notifications to the homeowner via SMS and e-mail
- In case of emergency if someone is home alone, there will be a panic button which can be utilized to notify other residents

### Project's purpose and scope

The purpose of this thesis is to give the insight about different ways of using the Raspberry Pi as a multifunctional device in particular as a basic home automation and a security system. For this reason, the Raspberry Pi capacities will be researched, as well as the main features of the device. There will be a detailed insight into the technical part of the project, special attention will be paid to the way the home automation and home security was created. Moreover, the information about the costs of the project will be provided.

### Methodology

In order to complete the paper, a working system is implemented. To test the system, real-life situations and scenarios are created and tested base on the information that is collected from the books and instructions. Of course, in order to use the available hardware and meet the personal needs some modification is done. The methods are the implementation of the system, testing the project and documenting the results.

## Background

This chapter will introduce the RasPi and its advantages over two other cheap single board computers. The reader can find the answer to this question: Why the RasPi is chosen for this thesis project?

The subject of home automation has been talked about over the past years. This chapter will briefly go through the concepts of home automation and home security. There are home automation products available off-the-shelf. The problem is that they are expensive and sometimes do not offer a solution to some personal needs. The chapter elaborates some of these problems.

### Why Raspberry Pi?

Today’s computer science students do not have the same skills like students in 1990’s, that is how Eben Upton felt. It might be due to the rise of more powerful computers and game consoles, so people do not have the programming skills of the earlier generation. That was the reason for the RasPi to come into the world with the help of Eben and his colleagues at the Cambridge University. (Richardson & Wallace 2013, vii)

It might be interesting to know where the name "Raspberry Pi" came from? The project at its early stages was called  “ABC Micro” by the founders. The name "Raspberry Pi" is originated due to the long tradition of giving  fruit names to computer parts and “Pi” comes from the word “Python”. The RasPi is not limited to using Python but it is the recommended programming language for the board. (Upton & Halfacree 2014, 4)

Python is one of a high-level programming languages, such languages are closer to a human language like English. It is developed by Guido van Rossum. Python’s goal is to provide a clear understandable syntax, which makes it a helpful tool for anyone who wants to learn to code. The programming language can be used on Windows, Linux and OS X. Python is available for free because it is published under an open-source license. (Upton & Halfacree 2014, 174)

One of the ways to interact with the RasPi through the internet is by means of the HTTP protocol, to accomplish that a web server like Apache can be used. The Apache web server is developed in 1995 by Rob McCool. Apache is open source software and the most popular web server on the market. In addition to Apache, there are other web servers that can be installed on the RasPi like Lighttpd which is designed to use less memory. installing a web server is enough to create a simple website but for developing a dynamic and more complex web pages a scripting programming language like PHP can be used. (Dennis 2013, 94; Upton & Halfacree 2014, 149)

The Raspberry Pi despite its small size is a functional computer capable of handling simple and complex projects due to its microprocessor. The board itself is about the size of a credit card, but it can process both video and audio. The RasPi has connectors that are used to communicate to other devices and the outside world, connectors such as Universal Serial Bus (USB), High-Definition Multimedia Interface (HDMI) and, of course, General Purpose Input/Output (GPIO) connectors. (Norris 2014, 1-5)

<a name="figure-1" />

<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/connectors.jpg">  
Figure 1: The Raspberry Pi and its connectors

Each GPIO can be controlled using a programming language like Python. A GPIO can be used as an input or output pin. Although RasPi’s operating voltage is 5V DC, it is important to remember that 3.3V DC is the maximum voltage a GPIO can be subjected to. Connecting a 5V supply to a GPIO will damage the RasPi. (Upton & Halfacree 2014, 222-223)

Raspbian is an operating system based on the Linux distributions, Debian. It is the recommended and supported operating system for the RasPi by the Raspberry Pi Foundation. Linux is open source which means there is no need to pay extra and buy its license. Linux is designed to be user-friendly and easy to learn that is why Linux applications contain “man page” which is short for manual page, it is a help file in order to provide details of how to use the software. (Upton & Halfacree 2014, 45-48)

So what can be done with the RasPi? There are new ideas people come up with all the time but, in general, it is possible to use the RasPi to build camera projects, games, set up a media center and do things that can be done with a regular computer. The advantage of the RasPi over a desktop PC is its GPIO pins. It is much more difficult to start a robotic project using a PC because of the lack of GPIOs. With the RasPi, such projects can be done straight away. The point is that the RasPi does not need to be dedicated to just one project, it can be used to accomplish several projects at the same time. (Upton & Halfacree 2014, 8-9)

Except the RasPi, there are other single board computers available to accomplish DIY projects. Boards like the Arduino and the BeagleBone Black but how to figure out which one is the best for a particular project. The best way, of course, is to look at these board’s features and abilities to choose the correct one. Let’s start with the board that is for beginners and used for single-purpose projects. The Arduino costs about €24, it is open source and consumes a little power. The Arduino does not have a graphical interface and it can be programmed using a computer.  As mentioned above the board is capable of doing simple single-purpose projects like controlling light by using a motion sensor. It is easy to find support for the Arduino since it is very popular. Despite the fact that it is designed for beginners, it still takes some times to get used to working with it. (Klosowski 2013)

The BeagleBone costs about €60 compared to the €40 RasPi. Unlike the RasPi, it does not need to be connected to a display in order to setup, because it is shipped with a pre-installed operating system. The board is designed for more advanced users, this is why it is not widely used for educational purposes. The BeagleBone has many GPIO pins which can be used to connect to a large number of external sensors and devices. Compared to the RasPi, the BeagleBone does not have as many USB connectors. It also does not include a camera connector or a display connector. The BeagleBone community is not as active as the RasPi community which means fewer tutorials and project ideas. If the project requires stronger processor and more RAM, the RasPi is advised but, on the other hand, a project that needs a lot of GPIOs is better carried out with the BeagleBone. (Gus 2015; Klosowski 2013) The main differences between the two devices are shown in Table 1.

<a name="table-1" />

||Raspberry Pi 2|Beaglebone Black Rev C|
|---|---|---|
|Processor|900MHz ARM Quad Core|1GHz ARM|
|RAM|1GB|512MB|
|Storage|MicroSD Card (Required) Expandable via USB|4GB on-board flash storage Expandable by USB & MicroSD|
|Audio|Stereo over HDMI, Stereo from 3.5mm jack|Stereo over HDMI|
|GPIO|26/40 Pins|65/92 Pins|
|HDMI|Full Size HDMI port|Mini-HDMI|
|Peripherals|4 USB ports, 1 10/100 Ethernet port, interface ports for Camera & Display|1 USB port, 1  10/100 Ethernet port|
|Power Source|Micro USB|Micro USB or 2.1mm jack|  
Table 1: Raspberry Pi 2 vs Beaglebone hardware chart (Gus 2015)

So, back to the main question of this part: Why the RasPi is chosen for this thesis project? Based on the background presented above the RasPi community is more vibrant and the board is designed for educational purposes, which unlike for the BeagleBone leads to more tutorials and ideas. Compared to the Arduino, the RasPi is capable of handling several tasks at the same time and that feature is a must for this thesis project.

### Home automation and security system

The 21st century is already the age of smart homes from the point of view of a person who lived in 1797 comparing the washing board or igniting a gas lamp to the washing machine and the light switch. So, are not we living in a smart home already? There is no need to touch a switch to turn on light, nowadays, a computer can do it automatically. But there is a difference between what someone needs and what someone wants. The bottom line is: a smart home must be able to save money. (Velte & Elsenpeter 2003, 3-7; Jenson 2014)

It is simple to automate the light for an extra cost, but is it really needed or does it really work as expected? The following examples help us to answer these questions: Walking into a room can turn on the light automatically but imagine someone is already sleeping in this room or while the wife is watching television, a system automatically dims the light, in the darkness, it will be pretty difficult for the husband to find a book from the bookshelf. But automation is needed at some level, for example, to turn off all extra lights and the heating system automatically when no one is home might be a good idea. (Velte & Elsenpeter 2003, 3-7; Jenson 2014)

The home automation system should not have any negative effect on human health. It is not a bad practice to stand up once in a while to make coffee or switch on the light traditional way using a light switch. New research shows that sitting more than six hours per day causes a premature death. While sitting the body will reduce burning fat by ninety percent,  the risk of diabetes increases by twenty-four percent and activitiy of leg muscles stops. (Johnson 2012)

Tellstick’s product is available in the market today. The label on its box says: “create your smart home”. The price of €169 includes a package which contains:

- Two remotely controlled sockets
- A thermometer
- One remotely controlled switch with dimming functionality
- A sensor that determines whether a door is opened

Another package that costs €209 contains three extra distantly controlled sockets plus a thermometer for the refrigerator. Product's users are able to control these devices locally and remotely. (Clas ohlson 2015)

But a smart home is not just about controlling light or some sockets. Here is an example of a functional home automation system. During the winter, the smart home starts to warm up the house at 5:30 in the morning because the alarm clock is set for 6:00 o’clock. The security system was functional all night so it is the time to turn it off automatically. In the day time, the children are at school and parents are at work, so the system will turn off all unnecessary devices like the cooker that is left on by mistake. The security system is turned on again. (Velte & Elsenpeter 2003, 4-7)

The homeowner can check on the family pet from work when he has a lunch break because the smart home can be interacted with by using a web-interface from a long distance. After a productive day, it is the time to go back home, so the system will turn on the coffee machine right before everyone’s arrival and raises the temperature in the house. When it is the time to go to sleep, the smart home starts playing relaxing music in all bedrooms as soon as people are in bed. The music will be turned off automatically later. (Velte & Elsenpeter 2003, 4-7)

The arrival of the RasPi changed the concept of the home automation drastically, it has the power of a PC and also can communicate with the environment around. It is possible to create cheap devices that are able to interact with some other home devices like the television by using the RasPi and a smartphone combined. Smartphones can act as a remote controller for these systems. Thanks to the RasPi, programmers are able to create software that manipulates their environment. The good news is that it also allows customization which leads to a personalized and a programmable home automation system. (Dennis 2013, 21)

A smart home is not much without a security system, but usually security systems are sold as a stand-alone service. There are ways, in general, to set up a security system: letting the security system take care of some automation like turning on the light or having the security functionality as a part of the smart home, so both systems can collaborate with each other. For example, it is possible to make the house look as if it is lived in by using some sensors to turn on the stereo and some lights if an intrusion occurs, even if the residents are on the other side of the world. The stereo can play a recording of a barking dog while the main lights are switched on. (Velte & Elsenpeter 2003, 9)

Based on the recent research smart homes are vulnerable and faulty sometimes. The real question is what we give up in order to sit more on the couch? There are no security standards to follow when it comes to home automation. It can take minimum about 15 seconds for a hacker to modify a remote controlled thermostat. While a compromised thermostat is not very harmful, imagine a stranger gaining access to the door lock or furthermore using a surveillance camera to spy on the children. Security attacks that a PC is more or less immune to can become harmful for today's smart devices like refrigerators or even the security systems. It is true that due to the immature technology our homes are less secure than a mobile phone or a PC. (Caroline 2015)

One of the test reports shows that ten out of ten security systems that are tested are not immune to the risk of unauthorized access. But there are steps that if taken can reduce the security risks. It is essential to use a very strong password and change all the product’s default passwords since it can be found easily on the internet or from the manual of the product in question. Wireless internet access is another vulnerability that should be paid attention to, a good password is also strongly advised in this case. Some of the modern routers allow the user to have more than one access point, it is a good practice to have an access point just for the home automation system. (Widman 2015)

Do not let any unauthorized person modify or even touch the system. A simple act of pressing “Restore Factory Defaults” button can open all the doors to a hacker. It is very important to make sure the homeowner is the only one who has access to the camera’s captured view, sometimes the data travels through a third party’s server and the remote control functionality is better to be switched off if not needed. It is good to mention that there is no foolproof method to guarantee the security, but let’s not make it too easy for the hackers. (Widman 2015)

G4S is a company that offers home security services for €39.90 per month. In addition to the company's services the price also includes:

- Three sensors that determine whether the doors are opened
- One motion sensor
- A motion sensor with camera
- Smartphone application and additional devices in order to control the security system

The price for each extra detail will be the following: one motion sensor is €55, a motion sensor with a camera is €120, a door sensor costs €55, an extra remote is €30 and the price for a smoke detector is €90. The customer must sign a contract for at least 24 months. It will cost €957.60 in total for the basic package. (G4S Kotiturva 2015)

## Implementation of a home automation and security system

### List of required sensors and devices

### Setting up the Raspberry Pi

### Home automation

#### WIFI sockets

#### Radio frequency sockets

#### Control a socket using home temperature

#### Control a socket using timer

#### Voice control

### Security system

#### Adding a wireless motion sensor

#### Sending SMS and triggering an alarm if motion is detected

#### Implementation of a panic button

#### Connecting a camera to the system

#### Capturing a video clip of an intrusion

#### Uploading the video to the cloud and sending an email notification

#### Controlling the security system via Bluetooth

### Creating a graphical user interface for the system

## Testing

## Ways to improve future implementations

## Conclusion

## References

Craig, Caroline. 2015. Smart home or dumb security risk?. URL: http://www.infoworld.com/article/2893600/mobile-technology/smart-home-or-dumb-security-risk.html. Accessed: 11.11.2015.

Clas ohlson. 2015. URL: http://www.clasohlson.com/fi/b/S%C3%A4hk%C3%B6/%C3%84lykoti/Aloituspaketit. Accessed: 09.11.2015.

Dennis, Andrew. 2013. Raspberry Pi Home Automation with Arduino. Packt Publishing Ltd.

G4S Kotiturva. 2015. URL: http://www.kotiturva.fi/. Accessed: 11.11.2015.

Gus. 2015. Beaglebone Vs Raspberry Pi 2: Choosing The Right Board. URL: http://pimylifeup.com/beaglebone-vs-raspberry-pi/. Accessed: 06.11.2015.

Jenson, Scott. 2014. The home automation paradox. URL: http://radar.oreilly.com/2014/02/the-home-automation-paradox.html. Accessed: 09.11.2015.

Johnson, Dave. 2012. Why sitting all day is killing you. URL: http://www.cbsnews.com/news/why-sitting-all-day-is-killing-you/. Accessed: 09.11.2015.

Klosowski, Thorin. 2013. How to Pick the Right Electronics Board for Your DIY Project. URL: http://lifehacker.com/how-to-pick-the-right-electronics-board-for-your-diy-pr-742869540. Accessed: 06.11.2015.

Norris, Donald. 2014. Raspberry Pi Projects for the Evil Genius. McGraw-Hill Education.

Richardson, Matt & Wallace, Shawn. 2013. Getting Started with Raspberry Pi. O'Reilly Media, Inc, USA.

Velte, Toby & Elsenpeter, Robert. 2003. Build Your Own Smart Home. The McGraw-Hill Companies.

Upton, Eben & Halfacree, Gareth. 2014. Raspberry Pi User Guide 2nd ed. John Wiley & Sons Ltd.

Widman, Jake. 2015. How to keep your connected home safe: 7 steps you can take to boost home security. URL: http://www.techhive.com/article/2894258/how-to-keep-your-connected-home-safe-7-steps-you-can-take-to-boost-home-security.html. Accessed: 11.11.2015.

## Appendix
