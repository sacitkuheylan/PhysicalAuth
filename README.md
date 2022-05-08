# Welcome to PhysicalAuth Main Repo!
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white) ![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white) ![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white) ![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white) ![IOS](https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=ios&logoColor=white) ![Raspberry Pi](https://img.shields.io/badge/-RaspberryPi-C51A4A?style=for-the-badge&logo=Raspberry-Pi)
<p align="center">
  <img width="250" height="250" src="https://i.ibb.co/3zzNH99/Physical-Auth-Logo50.png"  title="PhysicalAuth Logo">
</p>


Hi! :wave: Thank you for your interest in **PhysicalAuth**. This page intended to lead you through the project repositories. 


:warning:**Disclaimer**: This project is still in development and in alpha phase, not all features are available at the moment. Instructions to build and deploy to your devices are available at [repositories](#repositories)

**Expected relase date: :date: 20.05.2022**

# Table of Contents
 - [What is PhysicalAuth?](#what-is-physicalauth)
 - [Repositories](#repositories)
 - [Requirements](#requirements)
 - [State Diagram of PhysicalAuth](#state-diagram-of-physicalauth)
 - [Milestones](#milestones)
 - [Contribution](#contribution)
 - [LICENSES](#license)



# What is PhysicalAuth?
#### Project Description
  PhysicalAuth is a Hardware  **2FA** (Two-Factor Authentication) or **MFA** (Multi Factor Authentication) token generator that takes your token safety to next level. We all know that keeping our accounts are the most important thing in our digital life. That's why we use **2FA** (Two-Factor Authentication) or **MFA** (Multi Factor Authentication). Most of the time we use mobile applications such as Authy, GoogleAuthenticator, Microsoft Authenticator or LastPass Authenticator. We add our secret keys to those applications and it calculates us a **TOTP** (Time-Based One Time Password) for us.

Having our secret keys stored in a device that has **24/7** internet connection is not always safe. To prevent getting our secret keys or tokens stolen. I am proud to introduce you to **PhysicalAuth**.

#### What is TOTP (Time-Based One Time Password)
  TOTP (Time-Based One Time Password) is a generally 6 digit (sometimes 8) number sequence that is generated using a Base64 Encoded Secret Key. It has time interval of 30 seconds and it is calucluated using UNIX Time and Base64 Encoded Secret Key. As it has 30 seconds interval, it is not same and impossible to guess.
#### How does PhysicalAuth work?
  As mentioned in description, PhysicalAuth is a hardware-based token generator and it is compliant with **IETF RFC6238** (Internet Engineering Task Force) Standarts. All you need to do is wire up your hardware and install the mobile application (Available for **iOS** and **Android**/Developed using **Flutter**). Once you power up your device and install your mobile application. You can connect to your device from mobile application via LAN (Local Area Network). The device itself is isolated in your network and it does not send/receive packets outside yor LAN (Local Area Network). That's why your device is safe and convenient.   
# Repositories
  PhysicalAuth Project consists of 2 different software. You can access repositories through the links below. Each repository has their own detailed instructions at their **readme page**. In order to install and deploy **PhysicalAuth** correctly, you need to have Embedded Software and Mobile Application together.

 1. [Embedded Software written using **Python**](https://github.com/sacitkuheylan/PhysicalAuthEmbedded)
 2. [Mobile Application written using **Flutter**](https://github.com/sacitkuheylan/PhysicalAuthMobile)

# Requirements
  Hardware and Software Requirements are as following. I am still developing and testing with the hardware and software configuration below. There is no guarantee that PhysicalAuth will work on different hardware or software combinations.
 - Hardware 
 	 - A **Wi-Fi Capable** Development Board runs **Linux** (I have used **Raspberry Pi Model 3B+**)
	 - An OLED Screen (I have used 0.91" **SSD1306**)
	 - A Real Time Clock Module (I have used **PCF8523**)
	 - Some Jumper Wires
	 - A Push Button
 - Software
	 - A Linux Distrubution capable to run Python
	 - iOS or Android Mobile Device


# State Diagram of PhysicalAuth
  The state diagram below shows how PhysicalAuth works Embedded Software and Mobile Application Combined.

 1. If Hardware and Mobile Application is ready and Connected
 2. Hardware Starts to calculate tokens from Base64 Encoded Secret Keys and writes to LCD screen (This operation is continious)
 3. If new secret key added from mobile device, embedded software adds new secret key to database and at the same time token calclulation continues.

[![](https://mermaid.ink/img/pako:eNqdkj1rwzAQhv-KuaFDiZeOhhTSpNAS0qHOVnW46s6NqCwZWaoxIf-98kcGtyENuUncPe8jgW4P0hJDBrVHzyuFnw7L9PtOmCTW2-17kqb3yRM6atBx3kHzV0Zqp8DGfijNi6rSSqJX1vwhTygm6psYXlpjWHbxeR6k5LoesufsF0vOM70m39lmiVoGHfW0tV9sxvCpyT-RC-5LnosXbvrQgohpCP5q9mQ8xeaa261dPQzYpHXt8-P_DcSxYAYluxIVxZ3YdzMBfsclC8jikbjAoL0AYQ4RDRVF4SMpbx1kBeqaZ4DB27w1EjLvAh-hcbVG6vAD4p7WhQ)](https://mermaid-js.github.io/mermaid-live-editor/edit#pako:eNqdkj1rwzAQhv-KuaFDiZeOhhTSpNAS0qHOVnW46s6NqCwZWaoxIf-98kcGtyENuUncPe8jgW4P0hJDBrVHzyuFnw7L9PtOmCTW2-17kqb3yRM6atBx3kHzV0Zqp8DGfijNi6rSSqJX1vwhTygm6psYXlpjWHbxeR6k5LoesufsF0vOM70m39lmiVoGHfW0tV9sxvCpyT-RC-5LnosXbvrQgohpCP5q9mQ8xeaa261dPQzYpHXt8-P_DcSxYAYluxIVxZ3YdzMBfsclC8jikbjAoL0AYQ4RDRVF4SMpbx1kBeqaZ4DB27w1EjLvAh-hcbVG6vAD4p7WhQ)
> State Diagram of PhysicalAuth

# Milestones

 - [x] Create Wire Up Scheme
 - [x] Create RESTful API using Flask
 - [x] Create Mobile Application
 - [ ] Add Update/Delete Functionality to Mobile Application
 - [ ] Make Mobile Application UI Better
 - [ ] Design A Case for Device

# Contribution
  Everybody who is passionate about developing information security and also software is welcome to make contributions. You can open a pull request and write a summary about your contribution.

# LICENSE
[Embedded Software MIT License](https://github.com/sacitkuheylan/PhysicalAuthEmbedded/blob/master/LICENSE)

[Mobile Application MIT License](https://github.com/sacitkuheylan/PhysicalAuthMobile/blob/master/LICENSE)
