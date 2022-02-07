<h1 align="center">
  ☂️ WeatherStation
</h1>
<p>Weather station based on original Arduino UNO module with GSM module for sending weather status without Internet connection.</p>

<p align="center">
<img alt="Login" src="https://user-images.githubusercontent.com/38471368/152828967-59ff18a3-acc0-49f6-b7a5-916c5e6ee9d3.png" width="100%" height="auto" />
</p>
<p align="center">
<img alt="Login" src="https://user-images.githubusercontent.com/38471368/152828900-2b72d874-3101-475f-91c3-9720aa3736ab.png" width="100%" height="auto" />
</p>

<p>Considering the large size of the libraries, the whole system is composed of two modules. When Arduino UNO is initialized, it sends SMS notification about successful configuration. Arduino UNO get data in real time, then sends 1 SMS / 10 minutes with data to phone number hardcoded in program. ESP 32 receives data from the Arduino UNO connected via SERIAL BUS and displays the actual sensors data on the OLED display.</p></br>

<p align="center">
<img alt="Login" src="https://user-images.githubusercontent.com/38471368/148932544-e32cc40e-21a1-47da-b683-1f7eb73e5128.png" width="49%" height="auto" />
</p>



## Component pins:
### Arduino UNO:
 - ### DHT
   - 7
   
 - ### AirQualitySensor
   - 23 / A0
   
 - ### Barometer
   - SDA
   - SCL
   
 - ### SERIAL
   - RX / 0 ( Cross connection with ESP 32 )
   - TX / 1 ( Cross connection with ESP 32 )

### ESP 32:
 - ### OLED
   - SCK 22
   - SDA 21
 - ### SERIAL
   - RX2 / 16
   - TX2 / 17
  
## Description

### GSM Module

A-GSM II Shield GSM/GPRS/SMS/DTMF v.2.105 module is used for SMS communication.
It is a shield for Arduino UNO.
You can find it in libraries.rar file in main root of project.</br></br>

> :warning: This library requires that the program must be written in the file agsmII_kickstart0_9711.ino.  You cannot write a program in another .ino file

> :warning: Please insert SIM card into bottom card slot, otherwise module will not send messages properly.
</br></br>

### Pressure

To correctly setup the pressure sensor, a constant value must be read from the average pressure map for the region.

![Screenshot_9](https://user-images.githubusercontent.com/38471368/150375142-dd5a9fdf-01aa-4c7e-9b53-cd9174285010.png)

### Temperature & Humidity

Temperature and humidity are obtained using the DHT library.

### AirQuality

Air Quality is obtained using the Grove_Air_quality_Sensor library.


## 🚀 Quick start


### Visual Studio with Visual Micro or Arduino IDE
1. Arduino UNO
2. Connect via USB A-B cable
3. Build & deploy code from project: `WeatherStation/agsmII_kickstart0_9711/agsmII_kickstart0_9711.ino`

## 🛠️ Required Libraries

- SIM - agsmII_kickstart0_9711
- Pressure - Adafruit_BMP280_Library-master
- OLED - Adafruit_SSD1306
- AirQuality - Grove_Air_quality_Sensor 
- Temp & Humidity - DHT 

## 🧪 Technology Stack

- C++
