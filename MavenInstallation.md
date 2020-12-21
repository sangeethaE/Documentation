### Note : - Apache Maven requires Java.It was installed in the Previous Step.
##Install Maven
```
#cd /opt
#wget http://apache.mirrors.pair.com/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
#sudo tar -xvzf apache-maven-3.6.3-bin.tar.gz
#sudo mv apache-maven-3.6.3 maven 
#sudo nano /etc/profile.d/mavenenv.sh
#export M2_HOME=/opt/maven
#export PATH=${M2_HOME}/bin:${PATH}
#sudo chmod +x /etc/profile.d/mavenenv.sh
#source /etc/profile.d/mavenenv.sh
```
Verify Maven version:

#mvn --version

<image src="images/mavenVersionCheck.jpg"/>
