# FabScan PI - An Open-Source 3D Laser Scanner

[![Python Support](https://img.shields.io/badge/Python-2.7-green.svg)](https://www.python.org/)
[![Python Support](https://img.shields.io/badge/License-AGPL v3-blue.svg)](http://www.gnu.org/licenses/agpl-3.0.de.html)
[![Build Status](https://travis-ci.org/mariolukas/FabScanPi-Server.svg?branch=master)](https://travis-ci.org/mariolukas/FabScanPi-Frontend.svg?branch=master)

<img src="docs/images/logo.jpg" width="400">

## What is FabScan PI

The FabScan project started in 2010 at [Germany's first FabLab in Aachen](http://hci.rwth-aachen.de/fablab).The 
FabScan PI is the next iteration of the [FabScan 3D laser scanner](http://hci.rwth-aachen.de/fabscan). It uses a Raspberry PI and the Raspberry PI
camera module. The idea behind using a Raspberry Pi is to provide the same hardware setup for all FabScans.
Another benefit is that the FabScan gets a Stand-Alone, Web-Enabled 3D laser scanner.

The FabScan PI Server is written in Python. The Web-Enabled user inferface is written in JavaScript and HTML5 using WebGL. The code for 
the interface can be found at: http://github.com/mariolukas/FabScanPi-Frontend
That enables people with different programming skills to [contribute to this project](Readme.md#contribute).

FabScan PI is Free Software and released under the [GNU Affero General Public License V3](http://www.gnu.org/licenses/agpl.html).

## Documentation
The FabScan documentation can be found at [http://www.fabscan.org](http://www.fabscan.org)


##<a name="useage"></a> Useage

FabScan Pi is tested on: 


| Logo                            | OS             | Versions     | 
|:-------------------------------:|:--------------:|:------------:|
| <img src="docs/images/chrome-logo.png" width="30" height="30">  | OSX, Windows   | 47.0.2526.106 (64-bit) |
| <img src="docs/images/firefox-logo.png" width="30" height="30">  | OSX, Windows   | 43.0.4 |


By default the FabScan PI server binds to all interfaces on port 8080. Pointing your browser to 
[http://ip-of-your-raspbrry-pi:8080](http://ip-of-your-raspbrry-pi:8080) will open the user interface. If your computer supports bonjour
you can point yout browser to [http://fabscanpi.local:8080](http://fabscanpi.local:8080), you can omit the port if you used the SD-Card
image.


Most Apple devices support bonjour by default. On Windows you can install [Bonjour Print Services for Windows 2.0.2|
(http://support.apple.com/kb/DL999). You will find more detailed information about this topic for the most common 
operating systems [here](https://learn.adafruit.com/bonjour-zeroconf-networking-for-windows-and-linux/overview).

The main view provides a camera symbol. By clicking this symbol the live settings dialog appears. On the left side
is a laser detection preview. Best scan results can be reached, when the red laser line is covered by a blue line.

<img width="500" src="docs/images/main-view.png">

The coverage of the lines can be improved by using the different slider settings. A good point to start is the 
threshold slider. If the environment light is bright, try to set a lower value. If the environment light is low, 
you should better use a higher slider value. After chnangig the slider have a look at the preview image. The video
stream leaks for a few milliseconds, sometimes up to a second (depends on the environment lighting). More advanced
settings are the camera brightness and contrast settings and if you are using an LED ring/strip of course the 
RGB light setting, which can be used to increase the objects contrast level. A scan can be performed by clicking
the scan button in the first settings tab where the threshold and resolution slider are located.

<img width="500" src="docs/images/settings.png">

The resolution slider can be used to set the scan resolution. Sometimes it is better to start with a low resolution
to control the selected settings result. If the result is nice you can perform a higher resolution scan with the 
same settings. The current settings are persistent as long as the pi is up and running. The settings are also saved
with the scan data after a successful scan. They can be loaded to scan another object with the same settings. E.g. an 
object what consists of the same material, color etc. 

<img width="500" src="docs/images/loading-view.png">

The sharing dialog can be used to handle the current loaded scan. The sharing dialog provides options to download or 
delete a scan, and as already mentioned to load the scan settings. 

Previously scanned objects can be loaded by calling the load gallery dialog. A gallery of scans appears. By clicking
one of the previously scanned objects loads the scan.



## Contributions from
* Watterott electronic
* Beckmann Mediendesign (FabScanPi Logo)
* Doug LaRue 
* Jan Thar
* Rene Bohne
* Christoph Emonds
* Jan Borchers
