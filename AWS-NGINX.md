

# [Setting up an AWS EC2 instance with Ubuntu, Nginx, Route 53, and a free SSL certificate involves several steps.](https://www.linkedin.com/pulse/setting-up-aws-ec2-instance-ubuntu-nginx-route-53-ssl-selvanantham-erpxc/)

# EC2
## Create Instance
--
Ubuntu

name:
aws-nginx-0

Security Group:
aws-ninx-sg

HTTP: 80
HTTPS: 443

KeyPair:
AWS-nginx-kp-0

Storage:
30Gb

--

## SSH
```
ssh -i "AWS-nginx-kp-0.pem" ubuntu@ec2-13-42-36-62.eu-west-2.compute.amazonaws.com

```

## install NGINX
```
sudo apt update
sudo apt upgrade

sudo apt install nginx

```



