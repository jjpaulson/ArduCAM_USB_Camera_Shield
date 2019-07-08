# Overview

This is C/C++ ros code for the following cameras:

- MT9V022 (0.36MP Global Shutter Camera)
- MT9V034 (0.36MP Global Shutter Camera)
- AR0134/AR0135 (1.2MP Global Shutter Camera)
- MT9N001 (9MP Rolling Shutter Camera)
- MT9J001 (10MP Rolling Shutter Camera)
- MT9J003 (10MP Rolling Shutter Camera)
- MT9F002 （14MP Rolling Shutter Camera)
- MT9F001 （14MP Rolling Shutter Camera)
- OV2640 （1.9MP Rolling Shutter Camera)
- OV5640 （5MP Rolling Shutter Camera)
- OV5642 （5MP Rolling Shutter Camera)
- OV7675 （0.36MP Rolling Shutter Camera)
# Install library and OpenCV Environment
## Downlaod and install the latest libusb 
- Download the [libusb](https://sourceforge.net/projects/libusb/files/libusb-1.0/) 
- Copy the libusb-xxx.tar.bz to the Pi then run the following command to unzip it.[xxx：version number]
```Bash
tar -jxvf  libusb-xxx.tar.bz2  
```
- Before compilation, Run the following commands to config it  
```Bash
cd libusb-xxx 
./configure --disable-udev
```
- Install the libusb library 
```Bash
sudo make install
```
## Install Opencv and g++ compiler
- Install opencv
```Bash
sudo apt-get install libopencv-dev
```
- Install g++ compiler[the version number of g++ should more than 4.8]
```Bash 
sudo apt-get install g++-4.8
```

# Install the SDK
- Run the following command to install SDK
```Bash
make install-sdk
```
# Build your workspace
- In your ros workspace directory, run the following
```
catkin_make
```

# Usage
- In your ros workspace directory, make sure to run
```
source devel/setup.bash
```
- Then, run the camera node by running
```
rosrun arducam_ros_cpp arducam_ros_cpp_node "path to camera config file"
```
 
 example:
 
 ```bash
 cd "ros workspace"
 ```
 ```bash
 rosrun arducam_ros_cpp arducam_ros_cpp_node ~/catkin_ws/src/arducam_ros_cpp/cpp_config/AR0135.yaml
 ```
 
The topic published is /camera/image_raw

 While the program is running, you can press the following buttons in the terminal:	
 
    1.'s':Save the image to the images folder.	
    2.'c':Stop saving images.	
    3.'q':Stop running the program.	


