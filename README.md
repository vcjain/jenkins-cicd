# jenkins-cicd

# Installing Jenkins on Ubuntu 22.04

## For more details plese visit - https://pkg.jenkins.io/debian-stable/

### Steps to install Jenkins

Open terminal and execute below command

- curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null

- echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

 - sudo apt-get update
 - sudo apt-get install fontconfig openjdk-11-jre
 - sudo apt-get install jenkins

## Enable Jenkins Service
- sudo systemctl enable jenkins
- sudo systemctl start jenkins
- sudo systemctl status jenkins

## Get Initial Admin password
sudo cat /var/lib/jenkins/secrets/initialAdminPassword



