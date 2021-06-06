---
title: "必读"
description: "云易连是一个用来操控智能家居设备和访问私有云的软件，使用云易连可以轻易访问远程的设备和服务"
lead: "云易连是一个用来操控智能家居设备和访问私有云的软件，使用云易连可以轻易访问远程的设备和服务"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "summary"
weight: 100
toc: true
---

## 简介
云易连的目标是作为一个[通用的智能家居设备和私有云服务的接入和访问中心]()，你可以接入所有的开放联盟所定义的协议的设备或者接入包括米家、天猫精灵、小度、涂鸦、易微联等第三方设备。除了将这些第三方设备接入以外还可以提供插件[支持众多的第三方智能音箱]()的接入，[可以实现天猫精灵音箱控制小米的设备]()。当然智能家居硬件厂商也可以通过云易连的协议主动接入云易连生态。  
## 整体架构：

<img src="/images/arch.png" width = "500" height = "400" alt="架构" align=center >  
### 开源项目

本项目开源部分主要在如下几个项目地址：  
* [OpenIoTHub](https://github.com/OpenIoTHub):主要开源云易连的核心软件，包括APP(及插件)、网关、服务器等  
```
网关:https://github.com/gateway-go
自建公网转发服务器：https://github.com/server-go
```
* [IoTDevice](https://github.com/IoTDevice):主要开源物联网智能家居硬件及其协议、工具等，以下是主要的开源部分  
```
斐讯DC1接入云易连固件：https://github.com/IoTDevice/phicomm_dc1
斐讯TC1 A1接入云易连固件：https://github.com/IoTDevice/phicomm_tc1_a1
斐讯TC1 A2接入云易连固件：https://github.com/IoTDevice/phicomm_tc1_a2
廉价的ESP32摄像头：https://github.com/IoTDevice/ESP32-CAM
接入云易连的彩灯：https://github.com/IoTDevice/esp8266-RGB-WS2812
esp8266的单开关固件：https://github.com/IoTDevice/esp8266-switch
esp8266的串口穿透固件：https://github.com/IoTDevice/UART2TCP
esp8266温湿度计：https://github.com/IoTDevice/esp8266-dht11
esp8266的光照强度传感器：https://github.com/IoTDevice/esp8266-gy-30
```
* [mdnsService](https://github.com/mdnsService):主要开源私有云相关服务：包括私有云存储、远程桌面等服务

### 协议


