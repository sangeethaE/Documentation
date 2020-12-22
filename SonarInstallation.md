## Sonar Instllation Steps:

Login to the t2. medium instance as root user and follow below steps to install the SonarQube.

SonarQube required the java and Postgres installation

### Java Installation:
```
  #sudo add-apt-repository ppa:openjdk-r/ppa 
  
  #sudo apt-get update -y
  
  #sudo apt-get install openjdk-8-jdk
  
  #sudo update-alternatives --config java
  
  Verify Java version
  
  #java -version
  
```
 <image src="images/JavaVersionCheck.jpg"/>
 
### Postgres Installation:
```
#sudo apt-get update
#sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" >> /etc/apt/sources.list.d/pgdg.list'
#sudo wget -q https://www.postgresql.org/media/keys/ACCC4CF8.asc -O - | sudo apt-key add –
#sudo apt-get -y install postgresql postgresql-contrib
#sudo systemctl start postgresql
#sudo systemctl enable postgresql
```
Verify Postgres status using below command.
```
#sudo systemctl status postgresql
```
<image src="images/CheckPostgresStatus.jpg"/>

Login as postgres User
```
#sudo su – postgres
```
Create user sonar:
```
#psql
postgres=#ALTER USER sonar WITH ENCRYPTED password 'password';
postgres=#CREATE DATABASE sonar OWNER sonar;
postgres=#\q
#exit
```
### SonarQube Installation:
```
#sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-6.4.zip
#sudo apt-get -y install unzip
#sudo unzip sonarqube-6.4.zip -d /opt
#sudo mv /opt/sonarqube-6.4 /opt/sonarqube -v
#sudo vi /opt/sonarqube/conf/sonar.properties
```
Uncomment the below lines by removing # and add values highlighted yellow
```
sonar.jdbc.username=sonar
sonar.jdbc.password=password
```
Next, uncomment the below line, removing #
```
sonar.jdbc.url=jdbc:postgresql://localhost/sonar
```
Press escape, and enter :wq! to come out of the above screen.
```
#sudo vi /etc/systemd/system/sonar.service
```
add the below code in yellow color to the /etc/systemd/system/sonar.service file
```
[Unit]
Description=SonarQube service
After=syslog.target network.target

[Service]
Type=forking

ExecStart=/opt/sonarqube/bin/linux-x86-64/sonar.sh start
ExecStop=/opt/sonarqube/bin/linux-x86-64/sonar.sh stop

User=root
Group=root
Restart=always

[Install]
WantedBy=multi-user.target
#sudo systemctl enable sonar
#sudo systemctl start sonar
#sudo systemctl status sonar
```
Verify Sonarqube status.
```
#sudo systemctl status sonar
 ```
 <image src="images/chkSonarStatus.jpg"/>
 
Finally go to browser --> http://your_SonarQube_publicdns_name:9000/

Login Credenials for Sonarqube:

Username: admin

Password: admin

### Sonar-Scanner Installation Steps:
Download Sonar-Scanner using below wget
```
#sudo wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.5.0.2216-linux.zip
```
Unzip the Source
```
#unzip sonar-scanner-cli-4.5.0.2216-linux.zip
```
Set the SonarScanner properties in sonar-scanner.properties as shown below
```
#cd $install_directory/conf/

#vi sonar-scanner.properties

----- Default SonarQube server
sonar.host.url=http://localhost:9000
```
Create a configuration file in your project's root directory called sonar-project.properties
Set the SonarProject properties in sonar-project.properties as shown below

```
#vi sonar-project.properties

# must be unique in a given SonarQube instance
sonar.projectKey=my:project

# --- optional properties ---

# defaults to project key
#sonar.projectName=My project
# defaults to 'not provided'
#sonar.projectVersion=1.0

# Path is relative to the sonar-project.properties file. Defaults to .
#sonar.sources=.

# Encoding of the source code. Default is default system encoding
#sonar.sourceEncoding=UTF-8
```

