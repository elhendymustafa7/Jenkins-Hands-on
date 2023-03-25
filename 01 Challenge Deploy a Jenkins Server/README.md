# 01_02 Challenge: Deploy a Jenkins server
There are three basic requirements for this challenge:

1. Deploy a server running the latest version of Ubuntu Server.
1. Install NGINX as a proxy to Jenkins.
1. Install and configure Jenkins.

## Use a public cloud service
If at all possible, use a public cloud service for this challenge.

Suggestions:
- Amazon Web Services
- Google Cloud Platform
- Microsoft Azure
- Oracle Cloud
- Linode
- Digital Ocean

In later lessons, we’ll be implementing continuous integration from a code repo and your Jenkins server needs to be publicly accessible to allow a webhook to trigger jobs.

## Use locally available resources
If you aren't able to deploy Jenkins on a public cloud platform, please use the local system that you have available to you.

Jenkins runs on Windows, Mac OS, and Linux so you can install Jenkins just about anywhere.

_*PLEASE NOTE:* local installations will not be able to receive webhooks to trigger jobs._

However, You can still follow along with Jenkins installed on your local system.


## The Solution uses Amazon Web Services
The solution demonstrated in the course uses the Amazon web services public Cloud platform. Prerequisites to the solution include:

- Create a key pair for SSH connections
- Create an EC2 instance using a Ubuntu AMI
- Create an elastic IP for persistent DNS assignment

## Exercise files are available for this challenge.
There's a script that will update the Ubuntu OS, install NGINX, and install Jenkins. So you won’t have to do an installation from scratch.

- [jenkins-server-automated-installation.sh](./jenkins-server-automated-installation.sh)

The script also installs the suggested plugins and skips the installation wizard.

The script should work on any cloud platform as long as you use the Ubuntu Server operating system.

If you're following along and installing on a different operating system particularly Windows or Mac OS, review the course “Learning Jenkins” for detailed instructions on installing Jenkins on those platforms.

This challenge should take about 15 minutes to complete.

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

