## MiniKube Installation Steps

Login to t3.medium instance as ubuntu user and follow below steps to install the miniqube
Download the latest release with the command
      
```
 $curl -LO https://storage.googleapis.com/kubernetes-release/release/'curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt'/bin/linux/amd64/kubectl
	
```
 Make the kubectl binary executable
 ```
 $chmod +x ./kubectl
 ```
 Move the binary in to your PATH
  ```
    $sudo mv ./kubectl /usr/local/bin/kubectl
  ```
 Test to ensure the version you installed is up-to-date
  ```
   $kubectl version --client
   ```
 Docker install

```
$sudo apt-get update -y &&  sudo apt-get install -y docker.io
$sudo docker version
```
Minikube install
```
	$curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 
	$chmod +x minikube 
	$sudo mv minikube /usr/local/bin/
	$minikube version
```
Start minikube

```
$sudo -i
#minikube start --driver=none

```
Install the conntrack

```
  #apt install conntrack
  
```
Then, try to start minikube again

```
#minikube start --driver=none

```
Check the status of the minikube

```
#minikube status

```
Check the minikube using kubectl

```
#kubectl get pods
#kubectl get svc

```
