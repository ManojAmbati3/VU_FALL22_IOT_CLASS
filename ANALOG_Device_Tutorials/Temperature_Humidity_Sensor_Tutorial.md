Integrate the DHT11 sensor with Raspberry Pi for the temperature and humidity readings. 

Hardware: 

1. Raspberry Pi 

2. DHT-11 sensor 

3. Breadboard

4. 3 Jumper wires (Male to female) 
 

5. A 10K Ohm resistor

Process:

Connect the pins of the DHT-11 sensor and connect the jumper wires by following the circuit diagram
![PinSetup](https://user-images.githubusercontent.com/112664141/193221508-7a3b8ad8-b1fa-4550-aedf-86f937888957.jpg)
![How-to-Setup-the-DHT11-on-the-Raspberry-Pi-Four-pin-DHT11-Wiring-Diagram](https://user-images.githubusercontent.com/112664141/193221518-ad4336a5-3c63-4a3f-a616-5dff7e34d455.png)
Install WiringPi by cloning the WiringPi git

https://projects.drogon.net/raspberry-pi/wiringpi/download-and-install/ (Git link provided in this tutorial does now work so use https://github.com/WiringPi/WiringP)

Enter into the WiringPi directory and enter the command 'git pull origin' to make sure you the latest version.

To build, enter command './build'

Create a C program file and use the code provided in the tutorial and change the counter from 16→50. (Decreases the 'Data not good, skip' messages)

Use the command 'gcc -o HumidTemp HumidTemp.c -lwiringPi -lwiringPiDev' to execute the C file.

To run the file, use the command 'sudo ./HumidTemp'
![iot1](https://user-images.githubusercontent.com/112664141/193222110-239462a2-7cd0-43e5-8815-0cbd126d7e18.PNG)

References:

https://www.circuitbasics.com/how-to-set-up-the-dht11-humidity-sensor-on-the-raspberry-pi/

https://github.com/WiringPi/WiringPi

https://projects.drogon.net/raspberry-pi/wiringpi/download-and-install/

https://forums.raspberrypi.com/viewtopic.php?t=197331
