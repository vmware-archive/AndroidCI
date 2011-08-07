# Android CI
This project's purpose is to bootstrap Android continuous integration using 
Jenkins-CI (http://jenkins-ci.org/). This project is a stripped-down version of Jenkin's 
configuration directory, which is `~/.jenkins` by default. 

## Assumptions
We make the following assumptions. Feel free to deviate but you will likely need to fix some 
things as you go.

- You are working on a Mac
- Your android SDK is in ~/android-sdk-mac_x86, or you are going to put it there, 
or create a symlink, etc.

##AndroidCi and AndroidIntelliJStarter

AndroidCi ships with one preconfigured job: AndroidIntelliJStarter, which runs 
https://github.com/pivotal/androidintellijstarter. If your project started as a clone or fork of 
AndroidIntelliJStarter then Android CI will be very easy for you to set up. 

## Setting up Android SDKs.
Please see https://github.com/pivotal/androidintellijstarter for detailed instructions on setting up
Android SDKs.

## Bootstrap 

    git@pivotal:pivotal/AndroidCi.git
    cd AndroidCi
    ln -s $PWD $HOME/.jenkins


## Install and run Jenkins
Download the latest-and-greatest Jenkins: http://jenkins-ci.org/.  

Get the java one, not one of the native packages. 

Put it on your CI box.

launch jenkins:

    java -jar jenkins.war

## Configuring for your YourProject
Assuming you have a project named YourProject, which is based on AndroidIntelliJStarter:

- Visit Jenkins in your browser (http://localhost:8080 by default)
- Select AndroidIntelliJStarter
- Configure
- Update Project Name to YourProject
- Change GitHub Project
- Change Source Code Management => Git => Repositories
- Have a look at the Build steps to get a feel for what it does