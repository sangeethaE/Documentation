### Note : - Nexus requires Java.It was Installed in Previous Step.
##Nexus Installation:
```
#cd /opt
#wget http://download.sonatype.com/nexus/3/nexus-3.26.1-02-unix.tar.gz
#sudo tar -xvf nexus-3.26.1-02-unix.tar.gz
#sudo mv nexus-3.26.1-02 nexus
#sudo adduser nexus
```
Provide some password may be as admin, but do remember.
Keep pressing enter for all other values and press y to confirm the entries.
```
#sudo chown -R nexus:nexus /opt/nexus
#sudo chown -R nexus:nexus /opt/sonatype-work
#sudo vi /opt/nexus/bin/nexus.rc
change run_as_user="nexus"
sudo vi /etc/systemd/system/nexus.service
```
Copy the below content highlighted in yellow.
```
[Unit]
Description=nexus service
After=network.target

[Service]
Type=forking
LimitNOFILE=65536
User=nexus
Group=nexus
ExecStart=/opt/nexus/bin/nexus start
ExecStop=/opt/nexus/bin/nexus stop
User=nexus
Restart=on-abort 
[Install]
WantedBy=multi-user.target
#sudo systemctl enable nexus
#sudo systemctl start nexus 
#sudo systemctl status nexus 
```
Verify Nexus status as shown below:
<image src="images/VerifyNexusStatus.jpg"/>

Once Nexus is successfully installed, you can access it in the browser by 

```
URL - http://public_dns_name:8081
```

Login Credentials for Nexus: 

```
Username: admin
Password: admin123

```
