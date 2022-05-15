---
layout: page
title: Projects
permalink: /projects/
---
## [Arduino Data Acquisition with Python](https://github.com/lgmarin/arduino_dataaq)

Languages and Tools: [![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)

Data Acquisition software developed in Python as part of my Masters in Mechanical Engineering project. I was in need of a reliable way of measuring temperature in different points. 

The hardware built for this project allows for 5 different data points, collected by 5 MAX6675 Digital Converters by an Arduino Nano connected with a computer via USB port.

[![Arduino Data Acquisition with Python](https://github-readme-stats.vercel.app/api/pin/?username=lgmarin&repo=arduino_dataaq&show_owner=true)](https://github.com/lgmarin/arduino_dataaq)


## [Laboratory Management tool developed in Python/Flask](https://github.com/lgmarin/lab-manager)

Languages and Tools: ![](https://img.shields.io/badge/Code-Python-informational?style=flat&logo=python&logoColor=white&color=blue)
[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
![](https://img.shields.io/badge/Framework-Flask-informational?style=flat&logo=flask&logoColor=white&color=blue)
![](https://img.shields.io/badge/Tools-Bootstrap-informational?style=flat&logo=bootstrap&logoColor=white&color=blue)
![](https://img.shields.io/badge/Tools-Docker-informational?style=flat&logo=docker&logoColor=white&color=blue)

I created this app based on the needs of the Laboratório de Máquinas Térmicas at the Federal University of Paraná.

There is a lot of different users in the lab, on different projects (Engineering Projects, such as Formula SAE, Baja SAE, Aerodesing, etc), so the idea is to create a simple way for the students to create their account with basic data, and allow for the Professors responsible for each projects to validate their accounts.

[![Laboratory Management tool developed in Python/Flask](https://github-readme-stats.vercel.app/api/pin/?username=lgmarin&repo=lab-manager&show_owner=true)](https://github.com/lgmarin/lab-manager)







<!-- {% for repo in site.github.public_repositories %}

{% if repo.fork == false and repo.topics.size > 0 %}

## [{{ repo.name }}]({{ repo.html_url }})

{{ repo.description }}

Topics: {{ repo.topics | array_to_sentence_string }}

Last updated: {{ repo.updated_at | date_to_string }}

{% endif %}

{% endfor %} -->
