---
layout: page
title: Projects
permalink: /projects/
---

## [Laboratory Management Tool Developed in Python/Flask](https://github.com/lgmarin/lab-manager)

Languages and Tools: ![](https://img.shields.io/badge/Code-Python-informational?style=flat&logo=python&logoColor=white&color=blue)
[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
![](https://img.shields.io/badge/Framework-Flask-informational?style=flat&logo=flask&logoColor=white&color=blue)
![](https://img.shields.io/badge/Tools-Bootstrap-informational?style=flat&logo=bootstrap&logoColor=white&color=blue)
![](https://img.shields.io/badge/Tools-Docker-informational?style=flat&logo=docker&logoColor=white&color=blue)

I created this app based on the needs of the Laboratório de Máquinas Térmicas at the Federal University of Paraná.

There is a lot of different users in the lab, on different projects (Engineering Projects, such as Formula SAE, Baja SAE, Aerodesing, etc), so the idea is to create a simple way for the students to create their account with basic data, and allow for the Professors responsible for each projects to validate their accounts.

## [Arduino Data Acquisition with Python](https://github.com/lgmarin/arduino_dataaq)

Languages and Tools: [![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/) ![](https://img.shields.io/badge/Arduino-informational?style=flat&logo=arduino&logoColor=white&color=#00979D)

Data Acquisition software developed in Python as part of my Masters in Mechanical Engineering project. I was in need of a reliable way of measuring temperature in different points. 

The hardware built for this project allows for 5 different data points, collected by 5 MAX6675 Digital Converters by an Arduino Nano connected with a computer via USB port.

## [Meat Smoker Temperature Control IoT](https://github.com/lgmarin/defuma_IoT)

Languages and Tools: ![](https://img.shields.io/badge/Arduino-informational?style=flat&logo=arduino&logoColor=white&color=#00979D) ![](https://img.shields.io/badge/ESP-8266-informational?style=flat&logo=esphome&logoColor=white&color=blue) ![](https://img.shields.io/badge/C-++-informational?style=flat&logo=cplusplus&logoColor=white&color=blue)

Controller developed to display the smoker temperature with a buzzer to signalize the low and high temperature drops. The base system will be developed using an ESP8266 board, that allows for a Wifi Access Point connection that will expose a Web Server to display the temperature and allow to define the temperature thresholds on a smartphone or computer.

The hardware built for this project uses a MAX6675 Digital Converter for Type K thermocouple and a TM1637 Display.
