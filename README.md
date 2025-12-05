# FIEVel
### A Fast InExpensive Velocimeter based on an optical mouse sensor
<p align="center">
  <img src="https://github.com/harrislab-brown/FIEVel/blob/main/Images/mouse_sensor_overview.png" width="800">
</p>


# Repository Overview
Description of project folders and files as well as information how to get started with development.

A a full build guide for FIEVel is avalible in the repository wiki and linked [here.](https://github.com/harrislab-brown/FIEVel/wiki)

## CAD
CAD files were created in Autodesk Fusion360. Files are included in both .f3z Fusion archive format to retain parametric edibility, as well as STEP format for use with other CAD packages.

To open the files in Fusion, navigate to a project folder where you would like to add the files. From there the .f3z file can be uploaded and once processed all cad files should be available to edit. 

Model parameters for adjusting the focal length of the M12 lens and the desired magnification of the optical system can be accessed in the Design workspace. Design > Modify > Change Parameters will open a dialog box where model parameters can be edited. After modifying the magnification, it is common for a chamfer operation to break (don't know why). To fix, find the broken chamfer highlighted yellow on the bottom of the design workspace in the feature timeline.  Right click > Edit Feature on the broken chamfer and press OK. This will recompile the chamfer without changing any of the selected geometry or parameters.

## Firmware
Firmware in this project was adapted from the work of others. The library used to communicate with the ADNS3080 sensor was adapted from [RCmags ADNS3080 github](https://github.com/RCmags/ADNS3080) with minor modification to allow the use of a Teensy4.1 development board. RCmags' software was released under the MIT License which has been added as a header to all adapted files.

Original work on methods to increase the sample rate of the sensor is contained mostly in the /src/main.cpp file.

Flashing firmware to the Teensy has been tested using the PlatformIO and VS-Code. To flash the teensy, open VS-Code and install the PlatformIO IDE extension from the extension marketplace. From within platform IO, open an existing project and navigate to the /FIEVel/Firmware folder which contains the platformio.ini project configuration file. PlatformIO will request to install necessary dependencies to build and upload the Teensy4.1 project. 

A good tutorial for using PlatformIO with Teensy can be found at: [pjrc forum tutorial](https://forum.pjrc.com/index.php?threads/tutorial-how-to-use-platformio-visual-code-studio-for-teensy.66674/)
with the full documentation available at: [PlatformIO Teensy docs](https://docs.platformio.org/en/latest/platforms/teensy.html)

## Frame Capture
Visualization of the sensor image has been adapted from [RCmags frame capture github](https://github.com/RCmags/ADNS3080_frame_capture) with changes to allow the program to update faster. This faster frame rate is possible because of the higher communication bandwidth of both ADNS3080-Teensy SPI communication and Teensy-computer USB connection compared to the original documentation designed to work with an Arduino Uno. 

## License:
FIEVel is licensed under the CC BY-SA 4.0 Creative Commons license. 
