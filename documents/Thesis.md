# Home automation and security system with the Raspberry Pi

Ashkan Yaldaie

Bachelor Thesis  
HAAGA-HELIA University of Applied Sciences  
2 November 2015

## Table of contents
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

## Abbreviations and terms

<table>
  <tbody>
    <tr>
      <td>RasPi</td>
      <td>Raspberry Pi is a single-board computer</td>
    </tr>
    <tr>
      <td>GPIO</td>
      <td>General Purpose Input/Output</td>
    </tr>
  </tbody>
</table>

## Introduction

### Project questions and objectives

### Project's purpose and scope

### Methodology

In order to complete the paper, a working system is implemented. To test the system, real-life situations and scenarios are created and tested base on the information that is collected from the books and instructions. Of course, in order to use the available hardware and meet the personal needs some modification is done. The methods are the implementation of the system, testing the project and documenting the results.

## Background

This chapter will introduce the RasPi and its advantages over other cheap single board computers. The reader can find the answer to this question: Why RasPi is chosen for this thesis project?

The subject of home automation has been talked about over the past years. This chapter will briefly go through the concepts of home automation and home security. There are home automation products available off-the-shelf. The problem is that they are expensive and sometimes do not offer a solution to some personal needs. The chapter elaborates some of these problems.

### Why Raspberry Pi?

The Raspberry Pi despite its small size is a functional computer capable of handling simple and complex projects due to its microprocessor. The board itself is about the size of a credit card, but it can process both video and audio. The RasPi has connectors that are used to communicate to other devices and the outside world connectors such as Universal Serial Bus (USB), High-Definition Multimedia Interface (HDMI) and of course General Purpose Input/Output (GPIO) connectors. (Norris 2014, 1-5)

<img src="https://github.com/Ashkan-Yaldaie/thesis/blob/master/documents/img/connectors.jpg">

Each GPIO can be controlled using a programming language like python. A GPIO can be used as an input or output pin. Although RasPi’s operating voltage is 5V DC, it is important to remember that 3.3V DC is the maximum voltage a GPIO can be subjected to. Connecting a 5V supply to a GPIO will damage the RasPi. (Upton & Halfacree. 2014, 222-223)

Raspbian is an operating system based on the Linux distributions, Debian. It is the recommended and supported operating system for the RasPi by the Raspberry Pi Foundation. Linux is open source which means there is no need to pay extra and buy its license. Linux is designed to be user-friendly and easy to learn that is why Linux applications contain a help file known as “man page” which stands for manual page in order to provide details of how to use the software. (Upton & Halfacree. 2014, 45-48)

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

Norris, Donald. 2014. Raspberry Pi Projects for the Evil Genius. McGraw-Hill Education.

Upton, Eben & Halfacree, Gareth. 2014. Raspberry Pi User Guide 2nd ed. John Wiley & Sons Ltd.

## Appendix
