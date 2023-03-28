# Connect to node server using ssh

## create ubuntu ec2 instance 

![image](https://user-images.githubusercontent.com/58703269/227809101-e312416b-acc0-4ea3-b664-a108f48086f1.png)

## connect into ec2 to extract host and install prerequisites

- get hostname or ip address
```bash
hostname -I
```

- install java
```bash
sudo apt install default-jre -y
```
- install ssh
```bash
sudo apt install ssh -y
sudo /etc/init.d/ssh start 
```
- may need openjdk-11-jdk
```bash
 sudo apt install openjdk-11-jdk -y
```
- copy id_rsa (from master VM to jenkins Credential)
- copy id_rsa.pub (from master VM to slave or node VM) to authorized_keys

## create new node

- set Remote root directory => /home/ubuntu
- add host and Credentials
