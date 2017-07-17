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



# Over The Air(OTA)
OTA (Over The Air) means the programmer can code on local and send it to device to make it upgrade or replace with new firmware through the cloud. In Arduino, some developer finds a new way to update the Arduino sketch online. It makes developer who install the wireless Arduino device in a place where is difficult to touch can be update without uninstall.

![image](https://user-images.githubusercontent.com/29790334/28252674-b3accaae-6ad2-11e7-95bc-0a142a8a4633.png)

## nCube-Mint-OTA

In some case user have a kind of light weight WIFI device. Just like Arduino Yun or Arduino UNO with WIFI shield. And they can access internet directly without any gateway’s help. That is reason why we make &Cube-Mint software. It is a light weight C++ program for make a Adafruit Feather M0 WIFI board (A kind of Arduino M0 board) connect with Mobius-yt IoT Server Platform (More info in the IoT-Ocean Site). As mentioned above, the user maybe need to upgrade the program without touching. So, we support another software witch named &Cube-Mint OTA to help them upgrading the software throw the internet. 

![image](https://user-images.githubusercontent.com/29790334/28252678-cb023dba-6ad2-11e7-840a-825906fd25e0.png)

## Example

1. first firmware
- Open "File>Examples>oneM2MClient>nCube-Mint-OTA".
- Check	“FIRMWARE_VERSION”, "AE_ID" and "buildResource()".
- Upload sketch to board.

2. update firmware
- Check	“FIRMWARE_VERSION”, "AE_ID"(raise the version number).
- Compile the new ".Hex" file.
```
C:\Users\[user]\AppData\Local\Temp\arduino_build_********
```
- Open OTA Server website "http://203.253.128.161:8730"
![image](https://user-images.githubusercontent.com/29790334/28252742-16d533b8-6ad4-11e7-819a-b60ed5240421.png)
- Upload ".Hex" file.
- Send update command with HTTP request
```
POST /mobius-yt/[your-ae]/update
Host: 203.253.128.161:7579
Accept: application/json
X-M2M-RI: 12345
X-M2M-Origin: [your-ae]
Content-Type: application/vnd.onem2m-res+json; ty=4

{"m2m:cin":{"con":"active"}}
```
## OTA Result

![1](https://user-images.githubusercontent.com/29790334/28252773-fd39e984-6ad4-11e7-9cbb-8fd721186da6.png)

## Dependency Libraries

- ArduinoJson
- FlashStorage
- PubSubClient
- WiFi101
- WiFi101OTA
- TasCO2: CM1106 CO2 Sensor library(Made by KETI)
- OneM2MClient: Mobius client library(Made by KETI)
- OverTheAir: Device Online upgrade module(Made by KETI)

## Document

If you want known more detail, please refer the document below.

- nCube-Mint [instllation guide](https://github.com/IoTKETI/nCube-Thyme-Arduino/raw/master/doc/nCube-Mint_v1.0.docx)
- nCube-Mint-OTA [installation guide](https://github.com/IoTKETI/nCube-Thyme-Arduino/raw/master/doc/nCube-Mint-OTA_v1.0.docx)

# Author
Il Yeup (iyahn@keti.re.kr; ryeubi@gmail.com)
