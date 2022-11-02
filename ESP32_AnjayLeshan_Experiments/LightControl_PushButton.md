1. Clone the avs_commons repo using the following command in the projects directory. 

'git clone https://github.com/AVSystem/avs_commons'

2. Move into the avs_commons directory 

'cd ~/projects/avs_commons'

3. Build and install the avs_commons library

'cmake . && make && sudo make install'

4. Next we build and install the ANJAY Library by moving to the projects directory and clone the Anjay reopo

  'cd ~/projects'
  
'git clone https://github.com/AVSystem/Anjay'

5. Build the Anjay code

'cd ~/projects/Anjay'

'git submodule update --init'

'cmake . -DDTLS_BACKEND="mbedtls"'

'make -j''

6. Install the Anjay library objects by using the commands

'cd ~/projects/Anjay'

'cmake -DCMAKE_INSTALL_PREFIX=/home/dietpi/projects/Anjay-esp32-client . && make &&  make install'

7. To build the ANJAY client

'cd ~/projects/Anjay-esp32-client'

'cd ~/projects/Anjay-esp32-client'

'. $HOME/esp/esp-idf/export.sh'

'idf.py set-target esp32 '

8. To setup the device requirements

'cd ~/projects/Anjay-esp32-client'

'idf.py menuconfig'

9. In the blue screen, navigate to "Component->" and select config/anjay-esp32-client, which is located at the end of the list and enter Client options:

Set the config as: (anjay-esp32-client)

Endpoint name (coap://{LESHAN_SERVER_IP}:5683) (Mine was coap://192.168.8.221:5683, found in the leshan server page)

Server URI Choose socket (UDP), Choose security mode (Non-secure connection)

The configuration is done as shown in the scrernshots below

![bcb433c7-edc6-4f21-8d57-035e0129813d_Screenshot 2022-10-06 171827_full_retina](https://user-images.githubusercontent.com/112664141/199411601-92d57dc3-b2d3-4e7b-89c5-1b24751c593f.png)

Navigate to 'connection configuration' in the previous menu 

Enter the SSID and Password of your DietPI

![image](https://user-images.githubusercontent.com/112664141/199412260-6d8c53fe-7212-4159-b6b1-72f98a6782eb.png)

Next, move to board options in the previous menu screen and select 'Light control options'

Select 'Enable Red color' and enter the pin number where the LED is connected through jumper wire to the board. I have connected it to pin 5.

![d30cfa8a-95b0-4811-9e4e-400b88939bb0_Screenshot 2022-10-06 171718_full_retina](https://user-images.githubusercontent.com/112664141/199412005-7fe49f52-2e57-4ff7-a7cc-b8f8450a7c19.png)

Here is a circuit diagram used to connect the LED to the ESP32, found in the C_Tutorial in the Freenove tutorial
![bf55ade4-0493-4597-b5ae-cc8f4a207ad2_Screenshot 2022-10-06 172633_full_retina](https://user-images.githubusercontent.com/112664141/199412016-63cef473-2b31-4312-a395-4b8868311b79.png)
This is my circuit diagram and working LED 
![9ea478aa-bf3a-4e26-89c3-802ecfe000ea_IOT_LED_full_retina](https://user-images.githubusercontent.com/112664141/199412043-eb7617c0-a6a2-4246-b3f1-f02706ec7535.png)

![iott](https://user-images.githubusercontent.com/112664141/199412069-4c4bdfba-8c63-46b3-8727-6f887b8bd88a.jpeg)

![iot2](https://user-images.githubusercontent.com/112664141/199412081-8546e75e-18b3-4f43-931d-2b7ba7278862.jpeg)



References:
https://computing-sciences.yellowdig.app/community/62e2eacc-366d-319c-a96d-cf1e0b1d27ef?postId=47424135937107967
https://computing-sciences.yellowdig.app/community/62e2eacc-366d-319c-a96d-cf1e0b1d27ef?postId=47424135937086902
https://github.com/pschragger/IOT_Tutorials_for_VU/tree/main/RPI_BUILD_LWM2M_DEVICE
http://freenove.com/fnk0047
