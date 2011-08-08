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

##AndroidCI and AndroidIntelliJStarter
Android CI ships with one preconfigured job: AndroidIntelliJStarter, which runs tests and builds .apks 
for https://github.com/pivotal/AndroidIntelliJStarter. If your project started as a clone or fork of 
AndroidIntelliJStarter then Android CI's configuration should work well for you with only 
a few simple changes.

## Setting up Android SDKs
Please see https://github.com/pivotal/AndroidIntelliJStarter for detailed instructions on setting up
Android SDKs.

## Install AndroidCI 
Android CI is intended to be Jenkins' configuration directory, ~/.jenkins by default. 

1. Stop Jenkins if it is running
2. Move Jenkins' configuration directory out of the way if there is one.
3. Clone AndroidCI (or your fork) and set it as Jenkins' configuration directory

         git@pivotal:pivotal/AndroidCI.git
         cd AndroidCI
         ln -s $PWD $HOME/.jenkins

## Install and run Jenkins
Download the latest-and-greatest Jenkins: http://jenkins-ci.org/. Get the java one, not one of the 
native packages. 

launch Jenkins:

    java -jar jenkins.war

Jenkins will start using the ~/.jenkins directory set up above.

## Configuring for Your Project
Assuming you have a project named YourProject, which is based on AndroidIntelliJStarter:

- Visit Jenkins in your browser (http://localhost:8080 by default)
- Select AndroidIntelliJStarter
- Select Configure
- Update Project Name to YourProject
- Update the GitHub Project URL
- Update Source Code Management => Git => Repositories with your project's URL
- Look at the Build steps to get a feel for what it does

## Preinstalled Plugins
We have installed the following plugins in addition to the defaults:

- Git Plugin
- GitHub plugin
- Green Balls
- Radiator View Plugin
- Jenkins Rake plugin
- Hudson Ruby Plugin

