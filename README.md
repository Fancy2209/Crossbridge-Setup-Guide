# Crossbridge Setup Guide
![enter image description here](https://raw.githubusercontent.com/Fancy2209/fancy2209.github.io/main/crossbridge.io/design/crossbridge-170h.png)

A guide on how to setup the Crossbridge C/C++ Compiler for Adobe Flash Player on Windows

### While CrossBridge Community's fork technically works on Linux, I could not compile it and there is no binary distribution for the Linux version.
### If you discover how to compile CrossBridge, or have any ideas on how to improve this guide or problems with it, feel free to make a Issue or PR!

## Dependecy Setup
1. Download and extract the [Harman AIR SDK with New Compiler](https://airsdk.harman.com/download), and install [Java 8](https://www.java.com/download/)
2. Search for "Edit the System Environment Variables" and click on the option that shows up
   
![enter image description here](https://github.com/Fancy2209/Crossbridge-Setup-Guide/blob/main/System%20Variables.png?raw=true)

4. Click on this button on the window that pops up
   
![enter image description here](https://github.com/Fancy2209/Crossbridge-Setup-Guide/blob/main/Sys%20Vars.png?raw=true)

5. Add a variable called JAVA_HOME and set it to ``C:\Program Files\Java\jre-1.8``, than add a variable called AIR_HOME and set it to where the folder with the AIR files are
   
![enter image description here](https://github.com/Fancy2209/Crossbridge-Setup-Guide/blob/main/Sys%20Vars%204.png?raw=true)

6. Add to your path the bin folders in the AIRSDK and JRE folders like below
   
![enter image description here](https://github.com/Fancy2209/Crossbridge-Setup-Guide/blob/main/Sys%20Vars%203.png?raw=true)

## CrossBridge Community
1. Download [CrossBridge Community](http://sourceforge.net/projects/crossbridge-community/files/15.0.0/CrossBridge_15.0.0.3.zip/download)
2. Extract CrossBridge Community
3. Extract this [patch](https://github.com/Fancy2209/Crossbridge-Setup-Guide/raw/main/CrossBridge_Patch.zip) into the folder you extracted CrossBridge to, replacing files when asked to
4. Open run.bat and wait for Cygwin to install, when it finishes there should be a command prompt with a Cygwin shell, if you can't find it just run run.bat again
**NOTE: You have to use the run.bat everytime you want to open the Cygwin Shell**
To compile the samples:
```
cd $FLASCC_ROOT/samples
make FLASCC=$FLASCC_ROOT/sdk FLEX="$AIR_HOME"
```
It is reccomended to bump the Java Heap Size Limit
To do so run this command and re-open the Cygwin shell
```
export _JAVA_OPTIONS="-Xms512m -Xmx4096m"
echo export _JAVA_OPTIONS="-Xms512m -Xmx4096m" >> .bashrc
```
