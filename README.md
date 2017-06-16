# pepper-hack
This is a pepper Application that makes the Android Tablet usable on a Pepper 1.8a. So you can use it for debugging, install android apps on it, … 

## Background
For a few years now Softbank Robotics builds Pepper an humanoid robot with an android tablet. But since back then the Android tablet can't be used to actually run apps on it. Today when you want to use the android tablet you have to use a service on peppers main computer (the computer in peppers head) to display stuff on Pepper. Then they send adb commands to the tablet and you can display things like webviews (but not webkit or somthing ^^), images and videos (but max 15sec due to some technical limitations). But adb is really not made to communicate to a tablet in production. Often the tablet looses the connection and the webview on Pepper freezes. Because the Softbank Support couldn't help us for months, we had to hack our Pepper to install real android apps on it…

## How we did it
First of all we connected to pepper via ssh and looked trough stuff like the bootloaders and lots of shitty python code.At some point we found out how the tablet connection works and how we could kill applications on the tablet. This allowed us to remove the custom Applauncher made by Softbank and replaced it with the default android launcher. Than we installed Kingo SuperUser and Termux on the tablet (as sdks) and rooted it. This was necessary to get remote adb connections up and running. Afterwards we could just connect to pepper via android-studio (with the Pepper Plugin) and connect to the robot tablet.


