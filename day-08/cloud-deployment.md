# Day 08 - Cloud Server Setup: Docker, Nginx & Web Deployment

## Objective

Deploy a cloud server, install Docker and Nginx, configure security groups, and access the web server from the internet.

---

# Commands Used

## Connect to Server

```bash
ssh -i your-key.pem ubuntu@<public-ip>
```

## Update Server

```bash
sudo apt update && sudo apt upgrade -y
```

## Install Docker

```bash
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
docker --version
```

## Install Nginx

```bash
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
```

## View Nginx Logs

```bash
cd /var/log/nginx
cat access.log
```

## Save Logs

```bash
sudo cp access.log ~/nginx-logs.txt
```

## Download Logs to Local Machine

```bash
scp -i your-key.pem ubuntu@<public-ip>:~/nginx-logs.txt .
```

---

# Challenges Faced

* Initially SSH connection failed because the PEM file permissions were not correct.
* Nginx webpage was not opening because HTTP port 80 was not enabled in the security group.
* Learned how security groups act like firewalls in cloud servers.

---

# What I Learned

* How to launch and manage a cloud server using AWS EC2
* How to connect remotely using SSH
* How to install and manage services like Docker and Nginx
* How to check logs for troubleshooting
* Importance of security groups and firewall rules

---

# Why This Matters for DevOps

This task introduced real-world DevOps activities like:

* Cloud infrastructure setup
* Linux server administration
* Service deployment
* Remote access management
* Log analysis
* Security configuration

These are core responsibilities of DevOps and Cloud Engineers in production environments.

---

# Screenshots Added

* nginx-webpage.png<img width="1918" height="680" alt="Nginx webpage" src="https://github.com/user-attachments/assets/1010f9db-1aaa-4843-956b-d58c9ef6bd03" />
* nginx.png<img width="1361" height="365" alt="Nginx" src="https://github.com/user-attachments/assets/ae90c84c-1205-4a36-8c6a-867072de1119" />
* nginx logs [nginx-logs.txt](https://github.com/user-attachments/files/28403378/nginx-logs.txt)

122.177.109.63 - - [29/May/2026:13:01:38 +0000] "GET / HTTP/1.1" 200 409 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36"
122.177.109.63 - - [29/May/2026:13:01:38 +0000] "GET /favicon.ico HTTP/1.1" 404 197 "http://43.205.240.12/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/148.0.0.0 Safari/537.36"
2026/05/29 12:58:05 [notice] 12761#12761: using inherited sockets from "5;6;"


---

