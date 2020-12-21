###Docker Installation Steps:
```
#sudo apt-get update
#sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
#curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
#sudo apt-key fingerprint 0EBFCD88
#sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
#sudo apt-get update
#sudo apt-get install docker-ce docker-ce-cli containerd.io
```
Verify Docker status and version as shown below:
``` 
#sudo systemctl status docker
```
<image src="images/chkDockerStatus.jpg"/>

```
#sudo docker –version
```
<image src="images/CheckDockerVersion.jpg"/>
