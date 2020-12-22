## Gradle Installation Steps:

Prerequisites: Gradle requires a Java JDK version 7 or higher to run. 
You can <a href="https://systems-platform.github.io/Documentation/JavaInstallation">check here</a> on how to install Java on Ubuntu 16.04 if you don't have it installed. To check the version of Java that is currently set as the default, issue the command below:

java -version

### Step 1: Download and install Gradle

The distribution zip file comes in two flavours: Binary-only and Complete (all with docs and sources). We are going to download and install the Binary-only flavour for the purpose of this guide.
```
wget https://services.gradle.org/distributions/gradle-5.0-bin.zip
```
### Step 2: Unpack the distribution

Create a directory for the Gradle installation
```
sudo mkdir /opt/gradle
```

Extract the downloaded archive to the newly created directory.

 ```
 unzip -d /opt/gradle gradle-5.0-bin.zip
 ```
 You can view the contents of the directory using the command below:
 ```
 ls /opt/gradle/gradle-5.0
 ```
 ### Step 3: Configure your system environment
 For running Gradle, firstly add the environment variable GRADLE_HOME. This should point to the unpacked files from the Gradle website (the directory of the unzipped distribution)
```
export PATH=$PATH:/opt/gradle/gradle-5.0/bin
```
This is done in order for Gradle to be executable anywhere on the system.

### Step 4: Verifying installation
Issue the command below to run Gradle and display the version
```
gradle -v
```
hii
<image src="/./images/GradleVersionCheck.jpg"/>
