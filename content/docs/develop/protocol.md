---
title: "协议"
description: "云易连接入协议"
lead: "这里介绍云易连的接入协议"
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "develop"
weight: 110
toc: true
---

## 协议

云易连使用mdns协议来发现设备和服务，mdns声明云易连需要的数据，云易连将按照设备或服务声明的模型使用对应的UI插件访问。
## 服务声明
设备或服务必须以mdns声明为：_iotdevice._tcp

##  mdns的TXT
|  Key   | 含义  |  是否必须  |  值例子  |  备注  |
|  ----  | ----  |  ----  |   ---- |  ---- |
| name   | 名称 |  是  |  插座  |    |
| model  | 模型 |  是  |  com.iotserv.devices.plugin  |    |
| mac    | 物理地址 |  是  |  AA:BB:CC:DD  |    |
| id     | 唯一id |  是  |  3aa599ce-a409-40a9-b439-99046ffed0f7  |  推荐使用随机uuid  |
| author | 作者名 |  否  |  Farry  |    |
| email  | 联系邮件 |  否  |  abc@example.com  |
| home-page  | 主页 |  否  |  https://iothub.cloud/  |    |
| firmware-respository  | 开源固件地址 |  否  |  https://github.com/iotdevice/plugin  |    |
| firmware-version  | 固件地址 |  否  |  1.0  |    |

## 例子
Arduino：
```c++
  MDNS.addServiceTxt("iotdevice", "tcp", "name", deviceName);
  MDNS.addServiceTxt("iotdevice", "tcp", "model", "com.iotserv.devices.phicomm_dc1");
  MDNS.addServiceTxt("iotdevice", "tcp", "mac", WiFi.macAddress());
  MDNS.addServiceTxt("iotdevice", "tcp", "id", ESP.getSketchMD5());
  MDNS.addServiceTxt("iotdevice", "tcp", "author", "Farry");
  MDNS.addServiceTxt("iotdevice", "tcp", "email", "newfarry@126.com");
  MDNS.addServiceTxt("iotdevice", "tcp", "home-page", "https://github.com/iotdevice");
  MDNS.addServiceTxt("iotdevice", "tcp", "firmware-respository", "https://github.com/iotdevice/phicomm_dc1");
  MDNS.addServiceTxt("iotdevice", "tcp", "firmware-version", version);
```
