# 🚀 Jenkins on AWS EC2

This project shows how to install and set up **Jenkins** on an **AWS EC2 instance**.

## 🧰 Tech Stack
- AWS EC2 (Ubuntu 22.04)
- Jenkins
- Java 17

## ⚙️ Steps
1. Launch a Free Tier EC2 instance (t2.micro) with Ubuntu.
2. Open ports **22 (SSH)**, **80 (HTTP)**, and **8080 (Jenkins)** in the security group.
3. Install Java and Jenkins:
   ```bash
   sudo apt update
   sudo apt install openjdk-17-jre -y
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
     /usr/share/keyrings/jenkins-keyring.asc > /dev/null
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
     /etc/apt/sources.list.d/jenkins.list > /dev/null
   sudo apt update
   sudo apt install jenkins -y
   sudo systemctl enable jenkins
   sudo systemctl start jenkins
   
Access Jenkins at:
http://<EC2-public-IP>:8080
Unlock Jenkins using:
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Install suggested plugins, create a job, and add a user.

✅ Verify
Check if Jenkins is running:
sudo systemctl status jenkins

📸 Screenshots
EC2 instance
Jenkins dashboard
Job success
User created
