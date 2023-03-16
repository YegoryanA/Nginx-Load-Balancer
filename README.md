# Nginx-Load-Balancer
## Before starting please copy commands to instance user data, after that wait about 10 minutes and start using your instance.
## Don't forgett about Inbound rules ( 8080, 8081, 80, 22 ports must be opened )
## Enjoy!!!

##########################################################################################################
#!/bin/bash

sudo yum update -y
sudo yum install -y yum-utils curl
sudo yum-config-manager \
  --add-repo \
https://download.docker.com/linux/centos/docker-ce.repo

sudo yum install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo cu	rl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose \
sudo systemctl start docker \
sudo usermod -aG docker centos \
sudo systemctl enable docker.service \
sudo systemctl enable containerd.service \
sudo init 6
##########################################################################################################
