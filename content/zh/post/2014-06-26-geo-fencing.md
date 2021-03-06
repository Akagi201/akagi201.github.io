+++
title = "地理围栏(Geo-fencing)"
date = "2014-06-26T02:21:26+08:00"
slug = "geo-fencing"

+++

![geofencing](http://akagi201.qiniudn.com/geofencing.png)

## Geo-fencing

* A geo-fence is a virtual perimeter for a real-world geographic area.
* <http://en.wikipedia.org/wiki/Geo-fence>
* 地理围栏(Geo-fencing)是LBS的一种新应用, 就是用一个虚拟的栅栏围出一个虚拟地理边界. 当手机进入, 离开某个特定地理区域, 或在该区域内活动时, 手机可以接收自动通知和警告.
* 有了地理围栏技术, 位置社交网站就可以帮助用户在进入某一地区时自动登记, 可应用智能购物, 个人助理, 家庭成员/朋友的发现, 智能家居等领域.
* 地理围栏可通过蓝牙, WIFI, GPS等定位技术完成, 移动设备进入围栏后会自动选择最低功耗方式进行定位, 地理围栏技术为开发者提供全新想象空间.
* 地理围栏技术均是: 预先划定一些多边形的区域, 一个中心化的设备或者云端知道定位源进入该区域; 定位源知道自己进入该区域; 触发一些响应, 例如消息的push. 在智能硬件时代, 这种能够更加精准地定位, 更加节省功耗, 更加有效率低成本的互联互通方式, 迎来爆发机会.

## Geo-fencing vs LBS

* 地理围栏的地理区域是被网格化的. 网格化的标准是根据一个地理区域内的业务和商业聚类的, 而不是纯粹的经纬度和城市地图的匹配.
* 实际上地理围栏的各个围栏的区隔是一个个的应用需求群地图. 主要的商业需求聚集在特定区域, 形成的一个聚合信息服务区域.
* 终端自己或者在网络帮助下能够识别所处的围栏.
* 用户的围栏信息彼此之间能够共享, 也能够与应用开发商分享.
* 双向, 互动是关键.
* 商业群落是地理围栏的核心, 类似城市的商圈.
* 价值整合, 场景整合, 信息流资金流整合是关键.

## Geo-fencing vs Beacons

* <http://mashable.com/2014/02/24/beacons-geofencing-location/>
* <http://www.mobizou.com/geolocation-privacy-gaining-steam/>

## Geo-fencing Applications

### 百度的地理围栏技术

百度地理围栏技术是国内首家提供离线+在线地理围栏服务的产品, 基于位置的提醒和离在线结合的方式, 实现了功耗的大幅降低. 用户离关键位置点较远的时候, 会进行距离判断, 在用户到达围栏周围的时候, 再请求在线定位, 询问用户是否触发围栏.由于用户不需要一直打开GPS, 所以在使用该功能时达到了省流量, 省电的目的.

百度地理围栏技术"离线+在线"的技术策略, 能够让在用户体验上更为顺畅, 摆脱网络状况的限制, 避免智能手机普遍待机时间短的缺点, 极大提升了地理围栏的工作效率, 因此使用百度定位SDK提供的地理围栏服务的开发者能够设计开发更适合用户需求的产品. 目前, 已经有大量开发者利用百度地理围栏SDK开发相关应用, 精彩创意层出不穷.

### Intel的地理围栏技术

Intel的地理围栏技术采用了有效地将地理信息整合到移动平台的应用中去, 极大提高应用的易用性, 同时权衡系统待机时间与响应时间是Intel地理围栏的关键亮点, 实现了低功耗, 快速响应和高精度三者的完美结合, 其围栏技术的创新点:

1）使用MCU完成连续监测功能.

2）基于情境自动甑选合理的位置提供模块.

3）通过传感器轨迹推算实现实时定位和矫正.

Intel地理围栏技术亮点包括:

1）多定位源GNSS/Modem/WiFi.

2）传感器轨迹推算.

3）多地理围栏.

4）情境感知.

5）自适应.

### Apple的地理围栏 - iBeacons技术

iBeacon的出现让地理定位能够更加精确——从几百米的精度提高到了一米甚至半米. 这个精细度非常高的地理围栏, 终于可以让很多的实际物体都有条件具有了定义自己地理位置标识的能力, 例如一张桌子, 一把椅子, 都可以有自己的地理坐标.

苹果在iOS 7中推出的iBeacon协议包含两个部分:

1）按照苹果对iBeacon发射设备的数据流格式, 定制蓝牙设备广播, 那么这台低功耗蓝牙设备就可以被识别为iBeacon协议发射装置.

2）利用iOS设备对蓝牙的广播发出设备进行判断, 如果其发出的广播数据符合iBeacon的协议, 那么就认为这台低功耗蓝牙的发射装置是一台iBeacon基站.

由于iBeacon建立在蓝牙协议的基础上, 所以这个技术天然拥有了两个优势:

1）硬件的无缝过渡, 不需要硬件厂商投入成本进行完全不同的硬件开发.

2）现有数据传输协议对于用户来说没有太大迁移成本, 完全有能力像智能路由(Wi-Fi协议)一样成为物联网的数据中心节点.
      
### 其他的地理围栏技术

地理围栏技术在10年前便已出现. 在去年的Google IO大会上便已经有了地理围栏的展览.

Meridian平台便提供Zones地理围栏功能, 这项功能允许用户在开发者推出的室内地图App上随意用多边形圈区域, 而当用户真正到达这些区域时, app会立马推送通知. 除了Meridian, 国外还有几家地理围栏平台, 比如PlaceCast, Digby Localpoint, Wifarer和ShopKick. 和上述几家最大的不同是, Meridian是通过Wifi传感而非GPS定位.

而Google Lititude API也支持开发者在地图上标记多边形的围栏区域, App进入该趋于时便会收到push消息. 与iBeacons等技术不同的是, 这个push消息不是由基站发送, 而是云端推动的. 跟百度地图的地理围栏技术有些相似.

## Refs
* <http://www.leikeji.com/thread-546-1-1.html>