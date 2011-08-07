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
- AndroidCi ships with one preconfigured job: AndroidIntelliJStarter, which runs https://github.com/pivotal/AndroidIntellijStarter

## Android
Download the latest Mac SDK: http://developer.android.com/sdk/index.html

Unzip the archive and move the android-sdk-mac_x86 dir to ~/android-sdk-mac_x86. 
*This project assumes that android lives in ~/android-sdk-mac_x86*. You will need to 
fix paths in several places if you choose a different location.

Add the android tools to the PATH. 

    # Note: change .bash_pivotal to .bash_profile or .bashrc if needed
    echo "export PATH='$PATH:$HOME/android-sdk-mac_x86/tools'" >> $HOME/.bash_pivotal

Open a new Terminal window and run `android`:
 
    # in a new Terminal window:
    android 

Use the "Android SDK and AVD Manager" to download all of the SDKs you think you need.
If you need Google Maps then install the Google APIs under 
Available packages => Third party Add-ons.

Note: This project assumes you have SDK Platform Android 2.1 installed. You can change this in 
`default.properties`


## Bootstrap 

    git@pivotal:pivotal/AndroidCi.git
    cd AndroidCi
    ln -s $PWD $HOME/.jenkins


## Jenkins
Download the latest-and-greatest Jenkins: http://jenkins-ci.org/.  

Get the java one, not one of the native packages. 

Put it on your CI box.

launch jenkins:

    java -jar jenkins.war

******* Turn on build reports when ant is working********
add build release stuff