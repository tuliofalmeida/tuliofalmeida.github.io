---
layout: single
title: "JAMA"
excerpt: An open access device for measuring joint angles
header:
  teaser: jama_logo.png
collection: project
author_profile: true
share: true
---

![Jama_logo](https://github.com/tuliofalmeida/tuliofalmeida.github.io/blob/master/images/jama_logo.png "JAMA logo"){align=center}

Joint Angle Measurement and Acquisition device is open access hardware that was developed during my master's work at [Edmond and Lily Safra International Institute of Neuroscience](https://github.com/isd-iin-els) of [Santos Dumont Insitute](http://www.institutosantosdumont.org.br/unidade/instituto-neurociencias-iinels/). The function of JAMA is to measure joint angles wirelessly with 9 DOF, using a microcontroller (ESP32) together with an inertial measure unit (GY-80). Here we are providing all the codes and guidelines necessary to build this device and with the structure provided it will be easy to adapt to other sensors or microcontrollers. Together with JAMA, we developed a python library ([PyJama](https://github.com/tuliofalmeida/pyjama)) to analyze the extracted data using JAMA and other devices available on the market (IMU, MIMU, optical devices).
