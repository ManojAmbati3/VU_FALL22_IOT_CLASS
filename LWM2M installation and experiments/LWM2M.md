1.Login to your dietpi using the command ssh dietpi@DIETPIIPADDR and entering the password  <br>
2.Enter the command sudo dietpi-software and search for git in 'search software'<br>
  press spacebar to select '- Git: Clone and manage Git repositories locally' and press escape key<br>
  Search for JAVA in 'search software'<br>
  Select 'Java JDK: OpenJDK Development Kit' and select uninstall<br>
  Check if they are installed correctly by using the commands git --version and java --version<br>
![image](https://user-images.githubusercontent.com/112664141/192079673-6235338a-09b4-4da6-beab-b4919b079e4e.png)
  
3.Create a new directory 'download' and in that directory install the maven using <br>
  wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz<br>
  unpack by entering the command<br>
  tar xzvf apache-maven-3.8.6-bin.tar.gz<br>
  Add bin directory of maven to PATH using<br>
  sudo echo 'JAVA_HOME="/usr/lib/jvm/java-17-openjdk-arm64"' >> ~/.bashrc<br>
  echo 'PATH="${PATH}:/download/apache-maven-3.8.6/bin"' >>  ~/.bashrc<br>
  Check if they are installed correctly by using commands<br>
  'bash<br>
  mvn -v'<br>
4.Create a new directory 'projects' and in that directory clone the leshan repo using the command<br>
  git clone https://github.com/eclipse/leshan.git<br>
  To build leshan, go to leshan diretory and enter the command<br>
  mvn clean install<br>
  This build process may take a long time depending on the network traffic.<br>
  <br>
  Initially, my build has failed after building for almost 50 minutes. <br>
  ![PHOTO-2022-09-22-13-29-48](https://user-images.githubusercontent.com/112664141/192081434-e9935f07-a412-45d6-a125-d536967cfa28.jpg)
  I have changed the heap memory using the command<br>
  set MAVEN_OPTS="-Xmx512m"  (reference:https://stackoverflow.com/questions/42505638/maven-failing-to-assemble-war-java-heap-space-issue-stanford-core-nlp)<br>
  Then, I was able to build leshan.<br>
  ![image](https://user-images.githubusercontent.com/112664141/192081569-2db7248c-d02b-4060-ba7b-c06f03269d3d.png)
To start the leshan server enter the command<br>
java -jar leshan-server-demo/target/leshan-server-demo-*-SNAPSHOT-jar-with-dependencies.jar &<br>
 In the browser, enter the IP address of the diet pi followed by :8080 port<br>
 Run the leshan client using the command<br>
 java -jar leshan-client-demo/target/leshan-client-demo-*-SNAPSHOT-jar-with-dependencies.jar
 You can see your diet pi in registered clients.
 ![image](https://user-images.githubusercontent.com/112664141/192081734-082d90d2-7656-4f40-8a4f-7d07e8fdfa80.png)
  Tapping on DietPi gives more information about the client
  ![image](https://user-images.githubusercontent.com/112664141/192081857-e067d874-b089-4ff2-9d9b-cfa1744588ab.png)
  <BR>
  <BR>
  EXPERIMENTS<BR>
<BR>
  Enter the command 'sudo iwlist wlan0 scan' to display all the wifi networks available to the Raspberry Pi and their information.<br>
 (Reference: https://dronebotworkshop.com/raspberry-pi-cases/#:~:text=a%20wired%20connection.-,Scanning%20WiFi%20Networks,-One%20other%20test)
![image](https://user-images.githubusercontent.com/112664141/192082190-0271390b-7b0c-4781-bae2-b24df052716d.png)

Install wireshark and you can see the two way packets transfer between the PC and the Pi with their IP adddress.
  
![image](https://user-images.githubusercontent.com/112664141/192082024-ec23b1eb-caf0-422d-b6e9-692aaf1f75ab.png)

I ran the boostrap server using the command<br>
 java -jar leshan-bsserver-demo/target/leshan-bsserver-demo-*-SNAPSHOT-jar-with-dependencies.jar <br>                                          Go to leshan server page using DietPi IP ADDR:8080 and add client using clients configuration.(reference:https://github.com/eclipse/leshan#test-server-sandbox:~:text=You%20can%20also%20try%20our%20bootstrap%20demo%20server%3A)
  
![image](https://user-images.githubusercontent.com/112664141/192082029-aefef7d2-dc27-4bad-8367-95cb171f88f7.png)









Reference:https://github.com/pschragger/IOT_Tutorials_for_VU/tree/main/RPI_DEVICE_MANAGEMENT_INSTALL_tutorial
