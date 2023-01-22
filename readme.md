## Learning Jenkins
<!---
CI/CD process <img src="CICD.png" width="500" height="300" />
-->

# Table of Contents
- [Table of Contents](#table-of-contents)
  - [0. Introduction ](#0-introduction-)
  - [1. Install Jenkins](#1-install-jenkins)
  - [2. Jobs in Jenkins ](#2-jobs-in-jenkins-)
  - [3. More detail on jobs ](#3-more-detail-on-jobs-)
  - [4. Conlcusions ](#4-conlcusions-)


## 0. Introduction <a name="1"></a>
* Getting started with Jenkins
* What you should know
* Exercise files
* Why choose Jenkins?
* Key terminology
* Quiz
  * Question 1 of 1:  Where online can you access the exercise files for this course?
    * https://www.bitbucket.org
    * https://launchpad.net
    * https://sourceforge.net
    * https://github.com (Correct Answer)
## 1. Install Jenkins<a name="2"></a>
* System requirements
  * Can run with both personal computer or Server
  * Normally: Hardware: 256 MB RAM, 1 GB disk space;  Software: Java 11 or higher (JDK or JRE)
  * For Container: Hardware: 1 GB RAM, 10 GB disk space;  Software: Docker Personal Edition, Java is not required
* Install on Windows, Mac, Ubuntu.
  * Required: Administrator privileges, OpenJDK (11 or newer), Git Client, Jenkins
* Install Jenkins as Container:
  * Docker
    * docker pull jenkins/jenkins
    * docker image
    * docker run --detach --publish 8080:8080 --volume jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts
    * docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword //get pass from file for unblock Jenkins
    * open website with localhost:8080 to login and run as on windows or Mac or Ubuntu
* The Jenkins user interface
* Install and uninstall plugins
* Global tool configuration
* Quiz
  * Question 1 of 7: To install the latest version of Jenkins on a Mac using Homebrew, which command line would you type in the terminal?
    * brew install Jenkins 
    * brew services start Jenkins
    * brew reinstall openjdk
    * brew install java
  * Question 2 of 7: Which Docker command connects to the running container and prints the initial admin password for Jenkins?
    * docker exec jenkins cat /var/Jenkins home/secrets/initialAdminPassword (Correct Answer)
    * docker cat /var/jenkins_home/secrets/AdminPassword
    * docker exec jenkins /var/jenkins_home/initialAdminPassword
    * docker exec jenkins cat /var/secrets/AdminPassword
  * Question 3 of 7: If you are making changes at the system level for Jenkins on Ubuntu, you will also need to access your server as the _____ user.
    * regular
    * service
    * local
    * root (Correct Answer)
  * Question 4 of 7: Which menu item on the Jenkins Dashboard will you select to configure tools, their locations, and automatic installers?
    * Manage Jenkins (Correct Answer)
    * People
    * Build History
    * Lockable Resources
  * Question 5 of 7: If you want to uninstall a plugin, which tab would you select under the Manage Plugins menu?
    * Installed (Correct Answer)
    * Available
    * Updates
    * Advanced
  * Question 6 of 7: You are using Jenkins to configure Maven installations. Once you select Add Maven, what must you do next?
    * Give the configuration a name. (Correct Answer)
    * Select the version you want to use.
    * Select the Apply button.
    * Select the Install button.
  * Question 7 of 7: If you are running Jenkins as a Docker Container, what is the minimum RAM you will need?
    * 8 GB
    * 256 MB
    * 100 MB
    * 1 GB (Correct Answer)
## 2. Jobs in Jenkins <a name="3"></a>
* Your first Jenkins job
  * Go to Build after create new item.
  * Select "Execute Window Batch Command" for Window or "Execute Shell" for mac or linux
  * type "echo "Hello, Jenkins" " to test this item
  * Apply and Save.
  * Click build now and see the results.
* Jobtypes: check which type we can use
  * dsaf
  * asfa
* 

## 3. More detail on jobs <a name="4"></a>
* 
## 4. Conlcusions <a name="5"></a>
* 

