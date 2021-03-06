+++
title = "无线产品开发流程概述"
date = "2014-03-09T02:39:08+08:00"
slug = "wireless-device-workflow"

+++

本人做无线产品设计已经好多年, 做过的产品大概有三, 四十种, 简单的, 复杂的都有. 现如今我的设计一版成功的概率很大, 即使不能一版成功, 也可以在第一版中实现90%以上的功能, 性能, 朋友们因此还送给我了一下绰号"一版达人". 我想其实我也不是有多么深不可测的技术水平, 可能跟别人相比, 我最大的优点就是细心, 并善于思考. 我想在这里简单地分享一下我的心得体会, 我在这里想大概讲述一下无线产品的开发流程.

无线产品就是把物理接口上的数据转为在空间传输的电磁波. 物理接口就是CVBS, S/PDIF, HDMI, 网口, 串口, E1, T1, ADSL等, 具体采用什么接口由产品形态决定. 电磁波的特征, 如频率, 频宽, 调制方式等由相关的协议标准决定. 如蓝牙, Zigbee就是指定在2.4GHz频段运行的. 无线产品的硬件设计决定了产品的接口形式, 传输距离, 传输速度的问题. 软件设计决定了数据如传输. 这里主要探讨的是无线产品的硬件设计.

## 无线产品的七大功能模块

有了前面对无线产品的理解, 我把每个硬件产品都分为七大部分, 我想这应该是我首创的, 目前为止我还没有听过别的工程师这样说过.

![wireless-hardware](http://akagi201.qiniudn.com/wireless-hardware.png)

1. CPU+RAM+Flash, 又可以称为最小系统, 是整个产品的核心, 负责所有部分的正常运转.

2. 接口, 接口可以分为内部接口和外部接口. 内部接口用于产品内部不同器件之间的连接, 如PCI, MII, I2S, LVDS等. 外部接口是产品与外部进行通信的接口, 如网口, 音视频接口, 天线接口等.

3. 射频, 无线产品的射频设计是至关重要的, 整个产品的最重要的性能几乎全部体现在这里, 这部分在根本上决定了无线传输的距离, 可靠性.

4. 电源, 电源是整个产品的"营养供给", 保证了电源的"营养丰富, 健康", 才能确保产品整体的稳定性.

5. 时钟, 在大多数人眼中, 时钟可能都是一个不起眼的小角色, 但是, 在无线产品中, 很多实际问题都是由时钟及其附属电路引起的, 所以我向来都足够重视时钟电路.

6. 复位, 复位在整个产品中也许随处可见, 大部分芯片都需要进行复位, 可靠的复位是产品稳定工作的又一重要保证.

7. 按键, LED, GPIO, 有人可能会说, 这部分还值得一提吗? 我认为值得. 按键与LED是最直观的UI, 无线产品中的其他部分几乎都与UI无关, 同时, 按键, LED一般都是连接在GPIO上的, GPIO往往又起到上电配置的作用, 因此, 我认为GPIO很重要.

## 一般开发流程

![wireless-hardware-designflow](http://akagi201.qiniudn.com/wireless-hardware-designflow.gif)

## Refs
* <http://www.beamsky.com/topics/wireless-product-design-overview.html>