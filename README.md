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
