# SDK - ADB - Studio for Linux Ubuntu 18.04.02
Android

## ADB (Android Device Bridge)
**ADB or Android Debug Bridge**, is a command line utility that allows us to control an Android device from the computer itself. It is part of the Google Android SDK and can be used to execute shell commands or to copy files to the device and also to install or remove applications.

**Fastboot** is basically a diagnostic mode that is used to modify the Android file system of the computer when the android device is in bootloader mode. It is an alternative to recovery mode and is normally used to perform updates or to perform installations.

### Instalation
To install ADB & Fastboot on Ubuntu systems is pretty easy as the packages are available with the default Ubuntu repositories. To install both the ADB & Fastboot, execute the following command from the terminal,
```sh
sudo apt-get install android-tools-adb android-tools-fastboot
```
Once finished the installation can version check run this 

```sh
adb --version
```
and the machine return something like this:

```sh
Android Debug Bridge version 1.0.39
Version 1:8.1.0+r23-5~18.04
Installed as /usr/lib/android-sdk/platform-tools/adb
```
After the Beginning.
1. The ADB server will not init if not run

```sh
sudo adb start-server
```
2. For stop ADB service

```sh
sudo adb kill-server
```
 

Now to prove that your ADB installation is working well, we will connect an Android device to our system. But before connecting the Android device, we must make sure that the device has activated the option "USB Debugging". It can be activated by accessing device settings and developer options (some devices require you to tap the Android version in the About phone section several times to enable Developer Options).

Once USB debugging is enabled, connect the android device to the system using the USB cable.

Now open the terminal and execute the following command
```sh
adb devices
```

When executing the command you will get a popup window on your Android device to allow USB debugging, press OK to enable debugging. Now execute the same command mentioned above and we should see our device in the output of the list.

Note: If you obtain the permissions regarding the error after connecting the device, restart the ADB server and try again.

## SDK Android

View [Docs](https://en.wikipedia.org/wiki/Android_software_development)

For get* this please download the package [SDK Android](https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip)
Or

```sh
mkdir sdk-android
cd sdk-android
wget https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
unzip sdk-tools-linux-4333796.zip
```

and you'll get the folder *tools*, now we will have add the line to PATH. To end Line

```sh
nano ~/.bashrc
```
export PATH=${PATH}:/home/{usuario}/sdk-android/tools

Reset the machine and try
```sh
android
```

The software will open.

## Android Studio for Developers

View [Docs](https://en.wikipedia.org/wiki/Android_Studio)

1.- Install **Snap**
The Snap tool can be very useful for the installation of software packages. Snaps are software packages in containers that facilitate installation. No need to modify any file or write any command

```sh
sudo apt install snapd
```
[Can read this for more information about Snap](https://snapcraft.io/)

Now install from Snap dependences the Android Studio tools.

```sh	
sudo snap install android-studio --classic
```

Other way for will get the application [Graffic Mode]
Try

```sh
sudo apt update && sudo apt install libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 libbz2-1.0:i386 wget
java -version
mkdir Downloads
cd Downloads 
wget https://dl.google.com/dl/android/studio/ide-zips/3.1.4.0/android-studio-ide-173.4907809-linux.zip
sudo unzip android-studio-ide-*-linux.zip -d /opt/
cd /opt/android-studio/bin
./studio.sh
```





