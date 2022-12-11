Integrate the DHT11 sensor by using Arduino for the temperature and humidity readings. 

Hardware: 

1. Raspberry Pi 

2. DHT-11 sensor 

3. Breadboard

4. 3 Jumper wires (Male to Male) 

5. A 10K Ohm resistor

Process:

Install the Arduino application.(https://www.arduino.cc/en/software)

After installation, go to File->Preferences, add the URL (https://dl.espressif.com/dl/package_esp32_index.json) in the additional board manager section. Make sure the sketchbook location is a valid lcoation.

Go to Tools->Boards->Board manager and search for esp32, intsall the one by Espressif. After installation, select ESP32 Wrover Module in the board section.

Connect ESP32 to the PC, go to port and select the respective port that shows up.(Sometimes it does not show up any port, try reconnecting the ESP32 or using another USB port)

On left side of the screen, select Library manager and search for dht 11. Install the one by beegee-tokyo

In the .ino file, paste the code found on page 271 of the C_tutorial pdf in the freenove tutorial

Verify and upload the .ino file and go to serial monitor on top right after uploading is done.

Change the baud rate to 115200 and you can see the output.

![iot4](https://user-images.githubusercontent.com/112664141/193238820-82ebb0a5-79d0-4f1a-828f-b6a49bbfdfed.jpeg)


Code Snippet


![image](https://user-images.githubusercontent.com/112664141/206885753-5e659320-fa6b-453a-80a0-024c7a5ed72c.png)

Output in Serial monitor


![image](https://user-images.githubusercontent.com/112664141/206885766-f18400a3-ea73-471b-930d-c6626112b421.png)

Ref: https://freenove.com/fnk0047/


2.ESP8266 DHT11

I have tried to integrate DHT 11 with ESP8266, but maybe due to my wrong Circuit diagram setup, I get the error 'failed to read from DHT sensor'

![iot3](https://user-images.githubusercontent.com/112664141/193238785-99554a0a-44d3-4372-95db-d379f0423a7c.jpeg)

![iot2](https://user-images.githubusercontent.com/112664141/193226658-cc89dae9-b3c8-40d3-a539-9936c5d17035.PNG)
Ref:https://how2electronics.com/dht11-humidity-temperature-nodemcu-thingspeak/
