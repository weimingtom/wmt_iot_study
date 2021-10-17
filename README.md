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
