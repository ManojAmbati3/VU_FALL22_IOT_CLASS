                                                                       RPI Setup Tutorial

Devices information:
  •	The laptop I am using for this setup is a windows laptop. LAPTOP-9GN1OGC0.
  •	My router is a travel router- GL.iNet GL-MT300N-V2(Mango) Portable Mini Travel Wireless Pocket VPN Router
  •	Raspberry Pi 4 for setup
  •	A 32 GB SD card
Setup:
  •	Flash the sd card with your DietPi image using balenaEtcher
 ![balena](https://user-images.githubusercontent.com/112664141/190538807-2d74ef19-fa34-41cf-934d-af60ef1b3846.png)
 
  •	Open the contents of SD card and modify both dietpi.txt and dietpi-wifi.txt as follows.
1.	In the dietpi.txt file, change the following network default settings as,
#Language/Regional options
AUTO_SETUP_LOCALE=en_US.UTF-8 
AUTO_SETUP_KEYBOARD_LAYOUT=us
AUTO_SETUP_TIMEZONE=America/New_York 
AUTO_SETUP_NET_ETHERNET_ENABLED=0 
AUTO_SETUP_NET_WIFI_ENABLED=1 
AUTO_SETUP_NET_WIFI_COUNTRY_CODE=US
AUTO_SETUP_DHCP_TO_STATIC=1
AUTO_SETUP_NET_HOSTNAME=DietPi_MAMBA 
AUTO_SETUP_HEADLESS=1
AUTO_SETUP_AUTOSTART_TARGET_INDEX=1
SURVEY_OPTED_IN=0
CONFIG_SERIAL_CONSOLE_ENABLE=1

2.	In the dietpi-wifi.txt file, type in your SSID and password of your router in the SSID and KEY colums respectively.
aWIFI_SSID[0]='Manoj_IOT' 
aWIFI_KEY[0]='{password}'

  •	Insert the SD card into the PI and power it on. It will begin to flash red and green lights. After the green light has stopped blinking, which means that it has booted. This process may take from 5-10 minutes.
  •	 connect the PI to the Rouer and access the router admin page 198.168.8.1 on laptop.
  •	After logging in, go to the ‘clients’ section on left side and copy the IP address of my PI as you can see in the below image.

![image](https://user-images.githubusercontent.com/112664141/190539153-584e3fbe-6eb5-40ce-bea5-2c3e11b9e3ba.png)

  •	Open the command prompt and enter the command  “ssh root@IP of my Pi” and type the password and you will then enter the diet pi software as shown below.
  ![image](https://user-images.githubusercontent.com/112664141/190539229-45633adc-4bf5-4594-b69d-0b4c092982ab.png)
  
  •	A prompt will ask if you want to change the global software password for DietPi software installations.
  ![image](https://user-images.githubusercontent.com/112664141/190539313-7f4b2b91-766e-43bd-928e-17af4a2b7948.png)
![image](https://user-images.githubusercontent.com/112664141/190539322-dfce7a36-ab42-4212-9fd0-0c42844105d8.png)
![image](https://user-images.githubusercontent.com/112664141/190539357-b638e61e-868a-4ac4-bc85-66a9db1527da.png)

You have succesfully setup your PI.
Reference:https://github.com/pschragger/IOT_Tutorials_for_VU/blob/main/RPI_BOOT_WIFI_tutorial/README.md



