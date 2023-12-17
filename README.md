# jenkins-cicd 

This page will guide different steps required to setup a Jenkins and its pre-requisites. 
-----
# Install Java 17 
- sudo apt-get update
- sudo apt-get install openjdk-17-jdk

## Check Installation
- java -version

------ 

# Git 

## Installation 
- sudo apt-get update
- sudo apt-get install git-core
- git --version

## Generating SSH Key
- ssh-keygen      ----- generate key
- eval "$(ssh-agent -s)"  -- Start Agent
- ssh-add ~/.ssh/id_rsa   --- Add key in agent
- cat < ~/.ssh/id_rsa.pub 

------  

# Installing Jenkins on Ubuntu 22.04

## For more details plese visit - https://pkg.jenkins.io/debian-stable/

### Steps to install Jenkins

Open terminal and execute below command

- curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null

- echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

 - sudo apt-get update
 - sudo apt-get install jenkins

## Enable Jenkins Service
- sudo systemctl enable jenkins
- sudo systemctl start jenkins
- sudo systemctl status jenkins

## Get Initial Admin password
- sudo cat /var/lib/jenkins/secrets/initialAdminPassword



-----


# Install Maven

Download the Maven zip file at the below URL if you want to play with Maven on your local machine. If you want to use it on Jenkins then you can install Maven directly from Jenkins console.

Using package
- sudo apt-get install maven -y


##OR
Using zip file
- mkdir tools
- cd tools
- wget https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.zip
- unzip apache-maven-3.9.4-bin.zip

Check Installation
- mvn --version

-----

# Upgrade Jenkins on Ubuntu
Follow the below steps to upgrade the Jenkins instance to the latest in the current lab. 

### STOP Jenkins Service
- sudo /etc/init.d/jenkins stop

### Rename the Jenkins war file to war.old
- cd /usr/share/jenkins
- sudo mv jenkins.war jenkins.war.old
  

### Download latest war file
- sudo wget https://updates.jenkins-ci.org/latest/jenkins.war

### START Jenkins Service
- sudo /etc/init.d/jenkins start


------

# Git Practice commands

Below are some commands commonly used with Git to manage your code in repository. 
### Clone a git repo
- git clone <git url>

### Create a new branch
- git branch <branch name>

### Switch branch
- git checkout <branch name>

### Create and switch branch
- git checkout -b <branch name>

### Push the newly created branch to the remote 
- git push -u origin <branch name>

### Push change to remote branch
- git push

### Pull change to remote branch
- git pull

### Commit the change to the local branch
- git commit -m "Comment here"

### Adding a file to the stage area or index
- git add filename

### Remove a file to the stage area or index
- git rm --cached filename

### Remove all the uncommitted changes 
- git reset --hard

--------

### Install Docker using the below URL
- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04
Run the below command to run Jenkins as a docker container
- docker run  --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins:/var/jenkins_home -d jenkins/jenkins:lts-jdk17
- sudo docker logs jenkins



## Run SonarQube as Docker Container
- docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube


----------

### Installing Docker

- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04


