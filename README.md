# Simple Notes App
This is a simple notes app built with React and Django.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)



## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/NirmalNaveen20/django-notes-app.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`

# Install Docker on Ubuntu

### Updating list of packages

```
sudo apt update
```

### Install prerequisite packages:

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

### Setup GPG key for the system
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### Docker repository for APT sources
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

### Installing docker and docker-compose

```
sudo apt install docker-ce
```

```
sudo apt install docker-compose -y
```


# Install jenkins on ubuntu

### Install openjdk for jenkins

```
sudo apt install openjdk-17-jdk -y
```

### Add jenkins repository key to the system
```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

## Add repository list and authenticate jenkins
`curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
`

### Install jenkins by running
```
sudo apt install jenkins -y
```

### Start jenkins service
```
sudo systemctl start jenkins.service
```

### Check status of jenkins service
```
sudo systemctl status jenkins
```

### Get the first initial jenkins password
```
sudo more /var/lib/jenkins/secrets/initialAdminPassword
```

## Access jenkins panel
```
http://<ec2-public-ip-address>:8080
```

## Access django application 
```
http://<ec2-public-ip-address>:8000
```

## Dockerize Django Application
```
docker build -t notes-app .
```

## Start docker container
```
docker run -d -p 8000:8000 notes-app:latest
```

```
sudo usermod -aG docker $USER
sudo usermod -aG docker jenkins
sudo reboot
```

```
sh "docker-compose down && docker-compose up -d"
```

## Build the docker image
```
docker build -t notes-app .
```