# wmt_iot_study
My Wi-Fi / Bluetooth 2.0 / Bluetooth 4.0 (BLE, 2.4G) MCU driver code study

## Micro:bit  
* microbit-foundation/microbit-blue  
search weibo, micro:bit  
https://github.com/microbit-foundation/microbit-blue  
http://spotpear.cn/public/index/study/detail/id/398.html  
https://www.waveshare.net/wiki/KitiBot_for_micro:bit  
https://www.waveshare.net/wiki/Chapter_8_of_KitiBot_for_Micro:bit  

## RC522  
* MFRC522  

## 蓝牙串口是基于SPP协议（Serial Port Profile）  
我终于搞明白为什么大部分安卓客户端都无法连接上HC05这个蓝牙2.0模块，而amarino却能正常连接上。例如对于安卓官方提供的蓝牙2.0连接例子  
https://github.com/googlearchive/android-BluetoothChat/pull/30/files  
private static final UUID MY_UUID_SECURE =  
UUID.fromString("00001101-0000-1000-8000-00805f9b34fb");  
它使用的UUID跟amarino用的UUID不同，amarino使用的是SPP蓝牙串口的协议UUID，参考这里：  
手机标准蓝牙各类服务对应的UUID  
https://blog.csdn.net/chy555chy/article/details/52193659  
而大部分开源的安卓蓝牙连接代码用的不是同一个UUID，所以永远都无法对HC05模块建立起蓝牙连接，只要把UUID改成SSP的协议UUID就能正常连接得上了  

## 蓝牙模块HC05使用全记录  
https://www.jianshu.com/p/98987ef3f96e  
带小黑色按钮的，要选按着黑色按钮，然后再加电（即插上电脑的USB口）  
不带按钮的，要给KEY接线端接上一个电压（VCC），然后再插入电脑，即可  
当蓝牙模块state灯变为慢闪，则表明已经进入AT模式。  
作者：搬布  
链接：https://www.jianshu.com/p/98987ef3f96e  
来源：简书  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  

## iot
推荐去看零知实验室的文档：www.lingzhilab.com。  
那个可能是目前比较详细的教程，只不过你可能需要去买他的产品，应该也不会太贵  
物联网有几个方向：（1）需要做一个管理后台，这个不知道你会不会。例如上面资料中的物联网创新项目开发与实践.rar  
（2）使用ESP8266作为wifi模块，但需要另外一个单片机写程序，例如技小新的ESP8266，读取温度  
（3）简单通过手机或者网页来控制灯，但需要单独的路由器，例如零知实验室  
（4）通过一些在线平台，他们会提供SDK开发包甚至完整的例子，只要跑通就行，  
例如blinker平台。你看看哪种比较合适。零知和技小新应该比较简单，  
你也可以搜索一些物联网平台去看例子
更正一下，上次说的TKM32F499官方的物联网例子，操纵esp8266做无线透传的例子，  
应该是来源于野火的stm32f103的esp8266驱动代码，如果感兴趣可以看这个仓库：  
Embedfire-WiFi-esp/ebf_wifi_esp8266_code，在gitee和github上都有，  
或者搜索这个函数ESP8266_StaTcpClient_UnvarnishTest，  
应该也可以找到相关的TKM32F499的例子（主要是因为官方没有公开放出例子代码，  
这些代码要购买TKM32F499开发板才会给）  

## open62541  
https://github.com/open62541/open62541  

## MQTT broker    
* EMQ, MQTTX  
https://github.com/emqx/MQTTX  
Download the MQTTX server software and install it on the computer, and then configure the MQTT server.  
https://wiki.seeedstudio.com/Use_MQTT_to_remotely_light_up_LED_lights/  
Wio RP2040  
https://wiki.seeedstudio.com/Wio_RP2040_Module_Build-in_Wireless_2.4G/  
EMQ, EMQTT  
http://emqtt.com/downloads  
https://www.emqx.com/zh  

* mosquitto  
https://github.com/eclipse/mosquitto  
kwswitch  
https://github.com/kerwincui/kwswitch  

* OpenHAB+MQTT+NodeMCU实现远程控制, use EMQ    
https://blog.csdn.net/cnbeta1993/article/details/79066919  

* 自己做一个智能家居系统：NodeMCU+MQTT+OpenHAB改造灯开关篇  
https://augix.me/archives/5804  

* smart-swimmingpool  
https://github.com/smart-swimmingpool  
Project Smart Swimming Pool  
https://medium.com/diy-my-smart-home/project-smart-swimmingpool-4c40eb6741f6  

## ble_nus and ble_nus_c, in nRF5 SDK       
* A Web Command Line Interface via NUS (Nordic UART Service) using Web Bluetooth.  
* https://github.com/makerdiary/web-device-cli
* https://www.nordicsemi.com/Products/Development-software/nRF5-SDK/Download
* https://gitee.com/in_drama/smart-watch/blob/master/main.c
* https://gitee.com/in_drama/smart-watch-test-program/blob/master/app/src/main/java/com/example/myapplication/MainActivity.java
* fastble
* https://github.com/Jasonchenlijian/FastBle  


