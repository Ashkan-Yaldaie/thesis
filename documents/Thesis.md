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
  - [Testing](#testing)
4. [Ways to improve future implementations](#ways-to-improve-future-implementations)
5. [Conclusion](#conclusion)

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

### Project questions and objectives

### Project's purpose and scope

### Methodology

In order to complete the paper, a working system is implemented. To test the system, real-life situations and scenarios are created and tested base on the information that is collected from the books and instructions. Of course, in order to use the available hardware and meet the personal needs some modification is done. The methods are the implementation of the system, testing the project and documenting the results.

## Background

This chapter will introduce the RasPi and its advantages over other cheap single board computers. The reader can find the answer to this question: Why the RasPi is chosen for this thesis project?

The subject of home automation has been talked about over the past years. This chapter will briefly go through the concepts of home automation and home security. There are home automation products available off-the-shelf. The problem is that they are expensive and sometimes do not offer a solution to some personal needs. The chapter elaborates some of these problems.

### Why Raspberry Pi?

Today’s computer science students do not have the same skills like students in 1990’s, that is how Eben Upton felt. It might be due to the rise of more powerful computers and game consoles, so people do not have the programming skills of the earlier generation. That was the reason for the RasPi to come into the world with the help of Eben and his colleagues at the Cambridge University. (Richardson & Wallace 2013, vii)

The Raspberry Pi despite its small size is a functional computer capable of handling simple and complex projects due to its microprocessor. The board itself is about the size of a credit card, but it can process both video and audio. The RasPi has connectors that are used to communicate to other devices and the outside world, connectors such as Universal Serial Bus (USB), High-Definition Multimedia Interface (HDMI) and of course General Purpose Input/Output (GPIO) connectors. (Norris 2014, 1-5)

<a name="figure-1"></a>
<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/connectors.jpg">  
Figure 1: The Raspberry Pi and its connectors

Each GPIO can be controlled using a programming language like python. A GPIO can be used as an input or output pin. Although RasPi’s operating voltage is 5V DC, it is important to remember that 3.3V DC is the maximum voltage a GPIO can be subjected to. Connecting a 5V supply to a GPIO will damage the RasPi. (Upton & Halfacree 2014, 222-223)

Raspbian is an operating system based on the Linux distributions, Debian. It is the recommended and supported operating system for the RasPi by the Raspberry Pi Foundation. Linux is open source which means there is no need to pay extra and buy its license. Linux is designed to be user-friendly and easy to learn that is why Linux applications contain “man page” which is short for manual page, it is a help file in order to provide details of how to use the software. (Upton & Halfacree 2014, 45-48)

So what can be done with the RasPi? There are new ideas people come up with all the time but, in general, it is possible to use the RasPi to build camera projects, games, set up a media center and do things that can be done with a regular computer. The advantage of the RasPi over a desktop PC is its GPIO pins. It is much more difficult to start a robotic project using a PC because of the lack of GPIOs. With the RasPi, such projects can be done straight away. The point is that the RasPi does not need to be dedicated to just one project, it can be used to accomplish several projects at the same time. (Upton & Halfacree 2014, 8-9)

Except the RasPi, there are other single board computers available to accomplish DIY projects. Boards like the Arduino and the BeagleBone Black but how to figure out which one is the best for a particular project. The best way, of course, is to look at these board’s features and abilities to choose the correct one. Let’s start with the board that is for beginners and used for single-purpose projects. The Arduino costs about $25, it is open source and consumes a little power. The Arduino does not have a graphical interface and it can be programmed using a computer.  As mentioned above the board is capable of doing simple single-purpose projects like controlling light by using a motion sensor. It is easy to find support for the Arduino since it is very popular. Despite the fact that it is designed for beginners, it still takes some times to get used to working with it. (Klosowski 2013)

The BeagleBone costs about $50 compared to the $35 RasPi. Unlike the RasPi, it does not need to be connected to a display in order to setup, because it is shipped with a pre-installed operating system. The board is designed for more advanced users, this is why it is not widely used for educational purposes. The BeagleBone has a wide range of GPIOs which can be used to connect external sensors and devices. (Gus 2015; Klosowski 2013)

Compared to the RasPi, the BeagleBone does not have as many USB connectors. It also does not include a camera connector or a display connector. The BeagleBone community is not as active as the RasPi community which means fewer tutorials and project ideas. If the project requires stronger processor and more RAM, the RasPi is advised but, on the other hand, a project that needs a lot of GPIOs is better created with the BeagleBone. (Gus 2015; Klosowski 2013) The main differences between the two devices is shown in the Table 1.

<a name="table-1"></a>

||Raspberry Pi 2|Beaglebone Black Rev C|
|---|---|---|
|Processor|900MHz ARM Quad Core|1GHz ARM|
|RAM|1GB|512MB|
|Storage|MicroSD Card (Required) Expandable via USB|4GB on-board flash storage Expandable by USB & MicroSD|
|Audio|Stereo over HDMI, Stereo from 3.5mm jack|Stereo over HDMI|
|GPIO|26/40 Pins|65/92 Pins|
|HDMI|Full Size HDMI port|Mini-HDMI|
|Peripherals|4 USB ports, 1 10/100 Ethernet port, Camera & Display interface port|1 USB port, 1  10/100 Ethernet port|
|Power Source|Micro USB|Micro USB or 2.1mm jack|  
Table 1: Raspberry Pi 2 vs Beaglebone hardware chart (Gus 2015)

So, back to the main question of this part: Why the RasPi is chosen for this thesis project? Based on the background presented above the RasPi community is more vibrant and the board is designed for educational purposes, which unlike for the BeagleBone leads to more tutorials and ideas. Compared to the Arduino, the RasPi is capable of handling several tasks at the same time and that feature is a must for this thesis project. (Gus 2015; Klosowski 2013)

### Home automation and security system

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

### Testing

## Ways to improve future implementations

## Conclusion

## References

Gus. 2015. Beaglebone Vs Raspberry Pi 2: Choosing The Right Board. URL: http://pimylifeup.com/beaglebone-vs-raspberry-pi/. Accessed: 06.11.2015

Klosowski, Thorin. 2013. How to Pick the Right Electronics Board for Your DIY Project. URL: http://lifehacker.com/how-to-pick-the-right-electronics-board-for-your-diy-pr-742869540. Accessed: 06.11.2015

Norris, Donald. 2014. Raspberry Pi Projects for the Evil Genius. McGraw-Hill Education.

Richardson, Matt & Wallace, Shawn. 2013. Getting Started with Raspberry Pi. O'Reilly Media, Inc, USA.

Upton, Eben & Halfacree, Gareth. 2014. Raspberry Pi User Guide 2nd ed. John Wiley & Sons Ltd.

## Appendix
