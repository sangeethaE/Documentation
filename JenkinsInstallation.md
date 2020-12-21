Note : - Jenkins requires Java as PreRequisite.

###Jenkins Installation:

```
#wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
#sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
#sudo apt-get update -y
#sudo apt install jenkins
#sudo systemctl start jenkins
#sudo systemctl enable jenkins
#sudo systemctl status jenkins
```

Verify Jenkins status 

```
#sudo systemctl status jenkins
```

<image src="images/ChkJenkinsStatus.jpg"/>

Once jenkins is successfully installed, you can access it in the browser by 
```
 URL - http://public_dns_name:8080
```
Login Credential for Jenkins:

Username: admin

Password: Find the Password at /var/lib/jenkins/secrets/initialAdminPassword 

Add Jenkins users to sudoers  group:

```
#vi /etc/sudoers
jenkins ALL=(ALL) NOPASSWD:ALL
```
