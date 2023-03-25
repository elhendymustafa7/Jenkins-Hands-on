# Deploy a Jenkins Server

## Basic Requirement
- use latest version of ubuntu
- install NGINX as a proxy to jenkins
- install and configure jenkins
- use public cloud service

## Steps

- create ubuntu EC2 instance and allow ssh and http 

<!-- ![image](https://user-images.githubusercontent.com/58703269/227550563-a427be27-be8d-4591-988e-75bc92e9c2a7.png) -->
<img src="https://user-images.githubusercontent.com/58703269/227550563-a427be27-be8d-4591-988e-75bc92e9c2a7.png" alt="A cute puppy" style=" height: 200px;">

- allocate elastic ip and associated it to ec2 instance

![image](https://user-images.githubusercontent.com/58703269/227554385-1bf05312-8593-465b-a1c6-3f2cefd1b506.png)

![image](https://user-images.githubusercontent.com/58703269/227554589-27b3bb64-bdd7-4413-866e-749665fb1ad2.png)


- connect over ec2 using ssh

![image](https://user-images.githubusercontent.com/58703269/227556008-620d5344-2ceb-4689-8506-a4451c5b2862.png)

- add installation script 

![image](https://user-images.githubusercontent.com/58703269/227563635-1100343c-14ac-4b95-8670-b01151ff440f.png)

![image](https://user-images.githubusercontent.com/58703269/227563220-cd774c8d-be71-43ba-9804-567ac069cd9e.png)

- Run [installation script](./jenkins-server-automated-installation.sh) 

![image](https://user-images.githubusercontent.com/58703269/227565980-a909d273-3275-442f-aa62-4fec77853e39.png)

- Open jenkins in browser 

![image](https://user-images.githubusercontent.com/58703269/227569805-a7916f25-6499-4133-bb1a-f29418513a66.png)

![image](https://user-images.githubusercontent.com/58703269/227570182-cf8e3a26-318a-42cb-87db-4c42726159bc.png)

