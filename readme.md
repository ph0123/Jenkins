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
  - [4. Organize Jobs with Views and Folders ](#4-organize-jobs-with-views-and-folders-)
  - [5. Conlcusions ](#5-conlcusions-)


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
* Build description and source code management: we can pull and manage code from git, gitlab or bitbucket
* Build triggers:
  * Trigger builds remotely (e.g., from scripts): Need create a TOCKEN to do it.
  * Build after other projects are built: we can choose which project will be run before others
  * Build periodically: we can schedule it daily, weekly or monthly...
  * GitHub hook trigger for GITScm polling: Jenkins will run the project based on github activities with complex projects.
  * Poll SCM: should be chosen, it will track the commit activities.
* The build environment:
  * Delete workspace before build starts
  * Use secret text(s) or file(s).
  * Add timestamps to the Console Output: : Time out when can not receive outputs from the console.
  * Inspect build log for published build scans: Select "Execute Window Batch Command" for Window or "Execute Shell" for mac or linux
  * Terminate a build if it's stuck
  * With Ant: work with Java Ant.
* Run and monitor jobs
* Run and monitor jobs using Console output
* Monitor build trends: Click on "Trend" next to "Build History"; you can see timeline of historical build.
* Quiz
  * Question 1 of 7: You have created a new item using the Freestyle project type. To save your job configuration and keep working on it, what should you select?
    * OK
    * Save
    * Done
    * Apply(Correct Answer)
  * Question 2 of 7: You need to create a job that requires a series of steps to produce a final outcome. Which type of job is best to select?
    * Pipeline (Correct Answer)
    * Freestyle
    * Multi-configuration
  * Question 3 of 7: Why would you want to discard old builds?
    * to not exceed your allotted amount of builds
    * to erase any duplicate builds
    * to free up space on your server (Correct Answer)
  * Question 4 of 7: You want to trigger a job on a schedule. Which option under the Build Triggers section in Jenkins should you select?
    * Build after other projects are built
    * GitHub hook trigger
    * Trigger builds remotely
    * Build periodically (Correct Answer)
  * Question 5 of 7: Within the build environment section of Jenkins, where can you aggregate downstream test results?
    * under Additional Behaviors
    * under Credentials
    * under Add build step
    * under Post-build Actions (Correct Answer)
  * Question 6 of 7: You have started a job. Under Build History, what does it mean when there is a circle next to the build ID?
    * The job has been paused.
    * The job has not been run before.  (Correct Answer)
    * The job has been run before.
    * The job has no data collected.
  * Question 7 of 7: Under Build History, which mark indicates that your job was not successful?
    * a green checkmark
    * a red checkmark
    * a black x
    * a red x (Correct Answer)
## 3. More detail on jobs <a name="4"></a>
* Using a global build tool: Note about Git and Maven installation if needed.
* Source Code Management: 
  * add git URL
  * If repository is public, we dont need to add access tocken on "Credentials"
  * Build: Choose correct "Add build step", i.e. Java Maven: Invoke top-level Maven targets is selected.
* Browse a job's workspace
  * You can see all files and codes here.
  * Wipe Out Current Workspace on the lert to remove all files in the workspace.
* Manage Artifacts
* Parameters and environment variables
  * String: example: VERSION_NUMBER
    * We can use: echo $VERSION_NUMBER on linux or echo %VERSION_NUMBER% on window to see it.
  * Choice
    * We can add many options that we want
    * Ex: DEVELOPMENT, STAGING, PRODUCTION.
  * Boolen
    * Similar to choice parameter but it is true or false.
* Schedule Jobs
  * See it on Build Triggers -> Build periodically
  * Running job automatically
  * Updating sorfware
  * Check any problem with system
  * *****: minute (0-59), hour(0-23), day of month (1-31), month (1-12), Day of week (0-6: Sunday to Saturday)
* Quiz
  * Question 1 of 6: When adding a string parameter, which three things can you fill in?
    * the default value, the version, and the URL
    * the name, the URL, and the version
    * the name, the default value, and the description (Correct Answer)
    * the version, the command, and the description
  * Question 2 of 6: For choice parameters, if you enter DEVELOPMENT, STAGING, and PRODUCTION, which choice will be used as the default?
    * PRODUCTION
    * DEVELOPMENT (Correct Answer) - first option
    * All three choices will be set as default.
    * STAGING
  * Question 3 of 6: After you name your Boolean parameter, a checkbox parameter will be added to the build interface. If the box is checked, what will the run test environment variable be set to?
    * Active
    * Deployed
    * FALSE
    * TRUE (Correct Answer)
  * Question 4 of 6: Which open-source software must you have in order to use a global build tool in Jenkins?
    * GIT (Correct Answer)
    * Perforce
    * Bitbucket
    * Mercurial
  * Question 5 of 6: Jenkins makes it easy to manage artifacts with which tool?
    * Build Triggers
    * Post-build Actions (Correct Answer)- can clean before building jobs
    * Build Environment
    * Source Code Management
  * Question 6 of 6: To access parameters on a Windows system, which Build command shows the correct syntax?
    * %STRING_PARAMETER% (Correct Answer)
    * $STRING_PARAMETER
    * $STRING_PARAMETER$
## 4. Organize Jobs with Views and Folders <a name="5"></a>
* View and folders
* Create a view: Go to Dashboard to create and setting it.
* Create a folder: create item as create project but choosing folder.
* Delete views and folders
* Quiz
  * Question 1 of 2: You are creating a view and want to include all existing and new jobs with the word BUILD. What is the correct syntax for using a regular expression to include jobs in the view?
  * *BUILD_JOBS*
  * .BUILD_JOBS.
  * *BUILD*
  * .*BUILD.* (Correct Answer)
* Question 2 of 2: When you delete a folder, what happens to the contents of that folder?
  * The jobs and folders that the folder contains are deleted, but the views remain.
  * All the contents of the folder are deleted, along with the folder. (Correct Answer)
  * The folder itself is saved, but the jobs and views are deleted.
  * The views and folders that the folder contains are deleted, but the jobs remain.
## 5. Conlcusions <a name="6"></a>
* Pipeline as code 
  * Stored in a file named Jenkinsfile
  * Can be versioned in a code repository
  * Configure Jenkins jobs
  * Contain stages and steps
  * We can define stage with "Build", "Test", ... etc.
  * Steps is in a stage.
  * Chose Job Pipeline when create new item.
  * See Pipeline script and write the Jenkinsfile there.
* Continuing on with Jenkins
  * Can work with some other software that are similar to Jenkins.
  * Stackoverflow is a good page to discuss jenkins problem.
* Quiz
  * Question 1 of 1: The following code snippet shows stages of a pipeline. What must each stage also include?
      pipeline {
          stages {
                stage('Build') {
                }
                stage('Test') {
                }
          }
      }
    * three steps for each stage
    * a post-build action
    * at least two steps
    * at least one step (Correct Answer)