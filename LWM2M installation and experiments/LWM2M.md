1.Login to your dietpi using the command ssh dietpi@DIETPIIPADDR and entering the password  
2.Enter the command sudo dietpi-software and search for git in 'search software'
  press spacebar to select '- Git: Clone and manage Git repositories locally' and press escape key
  Search for JAVA in 'search software'
  Select 'Java JDK: OpenJDK Development Kit' and select uninstall
  Check if they are installed correctly by using the commands git --version and java --version
![image](https://user-images.githubusercontent.com/112664141/192079673-6235338a-09b4-4da6-beab-b4919b079e4e.png)
  
3.Create a new directory 'download' and in that directory install the maven using 
  wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz
  unpack by entering the command
  tar xzvf apache-maven-3.8.6-bin.tar.gz
  Add bin directory of maven to PATH using
  sudo echo 'JAVA_HOME="/usr/lib/jvm/java-17-openjdk-arm64"' >> ~/.bashrc
  echo 'PATH="${PATH}:~/download/apache-maven-3.8.6/bin"' >>  ~/.bashrc
  Check if they are installed correctly by using commands
  'bash
  mvn -v'
4.
  
  









Reference:https://github.com/pschragger/IOT_Tutorials_for_VU/tree/main/RPI_DEVICE_MANAGEMENT_INSTALL_tutorial
