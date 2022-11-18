#

# **PVI**
![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/PVI/Front%20page.png?raw=true)

# Table of Contents
- [**PVI**](#pvi)
- [Table of Contents](#table-of-contents)
  - [Intro](#intro)
  - [Brainstorming](#brainstorming)
  - [LSC Smartlight](#lsc-smartlight)
    - [System](#system)
    - [Support](#support)
    - [Execution](#execution)

#

## Intro
For my PVI I need to research and investigate technology with possible vulnerabilities. This way I can learn to scan for weak spots in a system. With these weak spots I would be able to give myself deeper acces or modify the software.

#

## Brainstorming
I asked around what kind of project they were going to do, and we gave eachother inspiration. After some ideas I wrote down what I possibly want to research. This means it had to be realistic to achieve, interesting to work with and maybe even usefull. 

![](./Pictures/PVI/Brainstorm.jpg)

After looking into these topics I really wanted to work with my LSC smart lights. In the LSC app you can automate some circumstances, but I'm missing some functions like turning on the lights when i'm close at home and it's dark outside. If I could get acces to the script the lightbulbs are running, I could modify or add code to make te light work as I want to.
#

## LSC Smartlight 
### System
I did some library research to find out what kind of technology the LSC smart lights have. The smart lights use an ESP8266 Wi-fi microcontroller. This means it could be possible to upload code over wifi if I use an arduino. Now I had to search for a library to be able to send code over a network.

The LSC lights from Action belong to a company called Tuya. The lights are connected to a server in China and communicate through my network which is not ideal. If I flash new software to my LSC lights it will overwrite the script to establish a connection with the Chinese servers. 
#

### Support
To flash the lights Over The Air, my laptop would need a wifi-adapter who supports Access-Point mode. When I open up device manager and look at my network adapters, I can see that I have a [Qualcomm QCA9377 802.11ac](https://www.qualcomm.com/products/technology/wi-fi/qca9377), but I can't find specifically if it supports AP-mode. Just to be sure I have a back-up Netgear router I can use as access point.

The flashing works with Linux, but I only use windows. This means I have to make an Ubuntu usb-stick to run without installing a whole new operating system.

Tasmota is open sourced firmware which can make a back-up of the current software running on my lights, which is very handy if the flashing goes wrong and flashing new software.  

Internet Of Things is a messaging protocol between physical or virtual machines over a network without needing a person to take actions. The requirement of using IoT is the machine needs to have an IP-address. 

MQTT is an common messaging protocol protocol for IoT which I can use to authorize communication between my devices.
#

### Execution
There are multiple ways to turn on/off the lights when i'm arriving or leaving, but I think the best way is to turn on the lights when my phone connects to my wifi. 

At first I had to setup my raspberry pi 4 by installing git and cloning the tuya-convert repository. I started the flashing progress and needed to connect a random device with wifi to the network my raspberry was sending. I put my light in pairing mode, but everytime my light did connect to the raspbery because it kept coming out of pairing mode, but I got an error saying "your device's firmware is too new".

I tried to look for possible ways to downgrade the firmware, but because of Tuya's security patch, it would need to happen serial.
  
#

## Smart TV

Because I tried to flash multiple LSC devices, Idecided to move on to a different project. I realized that I have a smart tv with TLC firmware which includes a few apps like Netflix. If I look at my parent's expensive Samsung tv it has apps like Disney plus and Spotify which my tv doesn't support.

## How do I customize my tv in to being smarter?
I did some research on what software I could use like kodi which I used to watch films and series on my laptop, but I know from experience what a pain in the ass it is to keep up with updates and subtitles. Then I looked into Android TV which contains all the apps I need and even more.

I formatted my raspberry SD card and installed Android 



