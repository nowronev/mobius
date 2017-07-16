# nCube-Thyme-Arduino
## Introduction
The nCube-Thyme-Arduino is a light version nCube for arduino device. In our project we also name it "nCube-Mint". The nCube-Mint is a kind of AE(oneM2M Resource Type) in software level. 

## Hardware
- Arduino Zero + WiFi Module or [Adafruit Feather M0 WiFi Board](https://www.adafruit.com/product/3061)

<div align="left">
<img src="https://user-images.githubusercontent.com/29790334/28243934-48f4f748-6a16-11e7-9c2c-42c0f320ca76.png" width="400">
</div><br/>

## Connectivity
In our sample source we show how to use Adafruit Feather M0 WiFi Board to connect CO2 sensor, RGB LED light and Relay module and make it work with the Mobius server platform.

![image](https://user-images.githubusercontent.com/29790334/28243956-0d773086-6a17-11e7-87d6-08d6fe3aa4d2.png)


- [CM1106 CO2 Sensor](http://www.gassensor.com.cn/pro/typeid/12/id/294.html)
- [Adafruit Power Relay FeatherWing](https://www.adafruit.com/product/3191)
- [RGB LED Module](http://alexnld.com/product/rgb-3-color-led-module-for-arduino-red-green-blue/)

## Installation

- Download the [Arduino IDE](https://www.arduino.cc/en/Main/Software).
- Install the Arduino IDE.
- Download the [nCube-Thyme-Arduino](https://github.com/IoTKETI/nCube-Thyme-Arduino/archive/master.zip).
- Copy the libraries file to Arduino IDE libraries folder.</br>
We provide the nCube-Mint source as Arduino libraries and you need copy or overwrite it to the Arduino IDE library home "c:\Users\[user name]\Document\Arduino\libraries". 

## Configuration

Adafrui Feather M0 is not an Arduino official device. So it needs some configuration to make the Arduino IDE work well with Adafrui Feather M0 device. These configuration detial that the developer can find it on the [Adafruit Feather M0 offical site](https://learn.adafruit.com/adafruit-feather-m0-wifi-atwinc1500/setup) or [nCube-mint guide document](https://github.com/IoTKETI/nCube-Thyme-Arduino/raw/master/doc/nCube-Mint_v1.0.docx).

## Running

- Connection the debug cable to PC<br/>
![image](https://user-images.githubusercontent.com/29790334/28244086-e1b366c2-6a1b-11e7-9188-76a5a860c30e.png)
- Open "File>Examples>oneM2MClient>nCube-Mint"<br/>

<div align="left">
<img src="https://user-images.githubusercontent.com/29790334/28244187-eff4f104-6a1d-11e7-93b6-1997d4054ab9.png" width="600">
</div>

- Open "Tools>Serial Monitor" for view the log.<br/>

<div align="left">
<img src="https://user-images.githubusercontent.com/29790334/28244217-f855df1a-6a1e-11e7-86ae-d09b2d438086.png" width="480">
</div><br/>

- Change the source as need.
- Click "upload" button on top of Arduino IDE.
- Connect pc WiFi to SSID "wifi101-3B3E".
- Open the link "http://wifi101.local".<br/>

<div align="left">
<img src="https://user-images.githubusercontent.com/29790334/28244236-aaba4556-6a1f-11e7-92db-ee807222bf45.png" width="400">
</div>

- Input the WiFi connection information on the page and click connection button.<br/>

<div align="left">
<img src="https://user-images.githubusercontent.com/29790334/28244247-fb989342-6a1f-11e7-8e89-6e33ad868291.png" width="600">
</div><br/>

<div align="left">
<img src="https://user-images.githubusercontent.com/29790334/28244248-0a759f90-6a20-11e7-8d7c-62e6a0e80fe6.png" width="600">
</div><br/>

## Dependency Libraries

- ArduinoJson
- FlashStorage
- PubSubClient
- TasCO2
- WiFi101
- WiFi101OTA

## Document

# Author
Il Yeup (iyahn@keti.re.kr; ryeubi@gmail.com)
