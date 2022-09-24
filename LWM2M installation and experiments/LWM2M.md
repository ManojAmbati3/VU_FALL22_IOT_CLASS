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
  Then, I was able to build leshan.
  ![image](https://user-images.githubusercontent.com/112664141/192081569-2db7248c-d02b-4060-ba7b-c06f03269d3d.png)



  









Reference:https://github.com/pschragger/IOT_Tutorials_for_VU/tree/main/RPI_DEVICE_MANAGEMENT_INSTALL_tutorial
