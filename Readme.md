# Windows, Unix, Raspberry Pi Motion Tracking Demo
### Uses python2/3, Opencv2/3 to do Real Time x,y tracking of largest moving object in camera view.
#### Motion Track Demo YouTube Video http://youtu.be/09JS7twPBsQ   
#### GitHub Repo https://github.com/pageauc/motion-track  

## Introduction
I did quite a bit of searching on the internet, github, etc, but could not
at the time find a similar python picamera implementation that returns x,y coordinates of
the most dominate moving object in the frame although some came close.

## Prerequisites
Requires Windows, Unix computer with a Web Camera or a Raspberry Pi computer with
a Web Camera or RPI Camera Module and an up-to-date Raspbian distro.
If you wish to use a web camera that is plugged into a usb port. Set WEBCAM = True in config.py
otherwise, WEBCAM = False will use a connected raspberry pi camera module video stream.
If running under Windows or a Not RPI unix distro then Web camera will automatically be
selected WEBCAM = True

The dependencies and code files can be installed per the motion-track-install.sh script
if you are using Debbian or Raspbian, Otherwise select the Github download zip or clone
option from the github repo here https://github.com/pageauc/motion-track
See Quick or Manual install instructions below for details

## Quick Install
Easy Install of motion-track-demo onto Debbian or Raspberry Pi Computer with latest Raspbian.

    curl -L https://raw.github.com/pageauc/motion-track/master/motion-track-install.sh | bash

From a computer logged into the RPI via ssh(Putty) session use mouse to highlight command above, right click, copy.
Then select ssh(Putty) window, mouse right click, paste.  The command should
download and execute the github motion-track-install.sh script and install the motion-track-demo.
This install can also be done directly on an Internet connected Raspberry Pi via a console or desktop terminal session and web browser.
Note - a raspbian apt-get update and upgrade will be performed as part of install
so it may take some time if these are not up-to-date

## Manual Install
From logged in RPI SSH session or console terminal perform the following.

    wget https://raw.github.com/pageauc/motion-track/master/motion-track-install.sh
    chmod +x motion-track-install.sh
    ./motion-track-install.sh

## How to Run
Default is console only display. Use Nano or text editor to Edit config.py
variable window_on = True
to display the opencv tracking window on GUI desktop. See other variables
and descriptions for additional variable customization settings.
From SSH session, console or GUI desktop terminal session execute the following commands

    cd ~/motion-track-demo
    ./motion-track.py

On Windows make sure you have the latest python installed from https://www.python.org/downloads/
Run motion-track.py from IDLE or if file association exists it can also be
run from cmd prompt by double clicking on motion-track.py.  Use a text editor
to modify config.py to view opencv window(s) and set other configuration
variables.

## Trouble Shooting
if you get an opengl error then see this article about installing opengl on  
a RPI P2  https://www.raspberrypi.org/blog/another-new-raspbian-release/   

Otherwise install opengl support library per following command then reboot.

    sudo apt-get install libgl1-mesa-dri

Edit the config.py file and set variable window_on = True so the opencv status windows can display camera
motion images and a circle marking x,y coordinates as well as
the threshold images.  The circle diameter can be change using CIRCLE_SIZE
variable.
You can set window_on = False if you need to run from SSH session.  If
debug= True then status information will be displayed without a GUI desktop session.

## Credits
Some of this code is based on a YouTube tutorial by   
Kyle Hounslow using C here https://www.youtube.com/watch?v=X6rPdRZzgjg   

Thanks to Adrian Rosebrock jrosebr1 at http://www.pyimagesearch.com   
for the PiVideoStream Class code available on github at   
https://github.com/jrosebr1/imutils/blob/master/imutils/video/pivideostream.py

## motion-track.py
Motion Track Demo - Basic concept of tracking moving objects.
This Demo program detects motion in the field of view and uses opencv to calculate the
largest contour above a minimum size and return its x,y coordinate.
* Motion Track Demo YouTube Video http://youtu.be/09JS7twPBsQ   
* GitHub Repo https://github.com/pageauc/motion-track   
* RPI forum post https://www.raspberrypi.org/forums/viewtopic.php?p=790082#p790082   


## ---------- Other Projects of Mine Based on Motion Tracking ------------

## track-inout.py
Track Enter and Leave Activity that cross a vert or horiz center line
This project Runs on Windows or Unix using Web Cam or Raspberry Pi using Web Cam or pi camera module
and Uses Python2/3, OpenCV2/3 to track motion and record object enter or leave camera view when
they cross a trigger centerline.
Has options to take image and/or record data in a csv file   
* GitHub Repo https://github.com/pageauc/track-inout  

## speed-camera.py
Windows, Unix vehicle (object) speed camera using motion tracking
Tracks vehicle speeds or other moving objects in real time and records image
and logs data. Now improved using threading for video stream and clipping of
area of interest for greater performance.
* GitHub Repo https://github.com/pageauc/speed-camera   
* YouTube Speed Camera Video https://youtu.be/eRi50BbJUro   
* RPI forum post https://www.raspberrypi.org/forums/viewtopic.php?p=1004150#p1004150   

## cam-track.py
Tracks camera pan/tilt motion position based on opencv template matching
Uses a clipped search image rectangle to search subsequent video stream images and returns
the location. Can be used for tracking camera x y movements for stabilization,
robotics, Etc.
* GitHub Repo https://github.com/pageauc/rpi-cam-track   
* YouTube Cam-Track Video https://www.youtube.com/watch?v=yjA3UtwbD80  
* Code Walkthrough YouTube Video https://youtu.be/lkh3YbbNdYg    
* RPI Forum Post https://www.raspberrypi.org/forums/viewtopic.php?p=1027463#p1027463          

## hotspot-game.py
A simple motion tracking game with motion activated menus
The game play involves motion tracking of body motion (hands) to get as many hits
as possible inside shrinking boxes that randomly move around the screen.
Position the camera so you can see body motions either close or standing.
Pretty simple but I think kids would have fun with it and they just might
take a look at the code to see how it works, change variables or game logic.
* GitHub hotspot-game Repo https://github.com/pageauc/hotspot-game   
* YouTube Hotspot Gam Video https://youtu.be/xFl3lmbEO9Y    
* RPI Forum Post https://www.raspberrypi.org/forums/viewtopic.php?p=1026124#p1026124   

## sonic-track.py
Send Motion Tracking Data to Sonic Pi to play notes and/or music samples
This demo app sends camera motion tracking data to the sonic-pi music program. 
sonic-track sends data to sonic-pi via psonic.py and pythonosc. You will need
a pi camera and a powered speaker connected to the Raspberry Pi audio/video 
plug via appropriate cables or you can attach RPI to an HDMI TV via HDMI cable
and sound will redirect to TV speakers.
* YouTube Air Drum Demo https://youtu.be/PSrzbeVX8DE
* YouTube Air Note Demo https://youtu.be/dC26PUYYR5E
* YouTube Motion Activated Menus https://youtu.be/PQjpskPAtR0

## ----------------------------------------------------------------------------


Have Fun
Claude Pageau   
YouTube Channel https://www.youtube.com/user/pageaucp    
GitHub Repo https://github.com/pageauc   

