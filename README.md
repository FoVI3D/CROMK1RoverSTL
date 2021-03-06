# CRO MK1 Rover STL
The CRO (Carry, Roam, Observe) MK1 Rover is FoVI3D’s autonomous vehicle research platform designed for single track hike & bike path/trail navigation research.

<p align="center">
  <img src = Img/CROMK1Rover1.png width="768">
</p>

## CRO MK1 Rover Processor Systems
The main CRO MK1 Rover processor is a 10W NVIDIA Jetson Nano which hosts a Quad-core ARM Cortex-A57 processor, 4 USB 3.0 ports, 2 MIPI-CIS(2) cameras connectors and 4 Gb of DDR4 RAM.  Motor controls and other real-time systems are offloaded to an Arduino Nano which sits on a common I2C bus.  Monochrome image capture and Simultaneous Localization and Mapping (SLaM) services are provided by an Intel RealSense T265 Tracking Camera.  The T265 has a pair of 163° fisheye, monochrome cameras, a Bosch BMIO44 Inertial Measurement Unit (IMU) and an Intel Movidius Myriad 2 Video Processing Unit (VPU).  RGB and depth image/point cloud capture services are provided by an Intel RealSense D435i Depth Camera.  The D435i depth capture is active IR stereo with an output resolution of 1280x720 at 90hz; the RGB resolution is 1080p at 30hz.  With the addition of an Intel Dual Band Wireless-AC 8265 W/Bt module, the Jetson Nano/CRO MK1 Rover has dual band 802.11ac Wi-Fi and Bluetooth 4.2.  Using a pair of 6dBi 2.4GHz/5GHz Wi-Fi antennas, CRO MK1 Rover has a wireless range of ~75-100m outdoors. 

Global Positioning Systems (GPS) services are provided by a serial Adafruit Ultimate GPS or a SparkFun I2C GPS module.  An I2C Adafruit LSM303 is used as an electronic compass and is located on a mast above magnetic inferences.  In the current CRO MK1 Rover configuration, there are also 2 USB 3.0 ports available for additional sensors/devices (such as LiDAR) and the common I2C bus can host additional sensors/devices as required.

<p align="center">
  <img src = Img/CROMK1RoverProcessorSystem.png width="768">
</p>

## CRO MK1 Rover Power System
The current CRO MK1 Rover power system consists of a pair of 7.2V 5000mAh 6-Cell NiMH batteries (LiPO is also an option) and a DROK adjustable step-down buck converter/regulator.  One battery supplies 5V power to the processor system through the buck converter/regulator.  The second battery is currently used to power the powertrain.  When the processor system is fully loaded, a single battery can power the system for ~3 hours.  When both batteries are configured in parallel for the processor system, the CRO MK1 Rover can operate for ~6 hours between charges.  The power system can be extended for prolong use if necessary.

<p align="center">
  <img src = Img/CROMK1RoverBatterySystem.png width="768">
</p>

## CRO MK1 Rover Powertrain and Chassis
The current CRO MK1 Rover powertrain and chassis is a 2WD Traxxas Stampede stripped of body, mounts, and the RF receiver system.  The Traxxas Stampede provides an excellent platform for robotic trail/path navigation research, having a simple, high-clearance, rugged suspension system and a top speed of ~30mph.  The Traxxas Titan 12-turn 550 motor and XL-5 Electronic Speed Controller (ESC) are reliable and easily upgradable.  The ESC and steering servo control signals are managed by the Arduino micro-controller.   The CRO MK1 Rover body was custom designed by FoVI3D to be easily printed and assembled.  

<p align="center">
  <img src = Img/CROMK1RoverPowerTrain.png width="768">
</p>

## CRO Robot Operating System (CRos)
Since conservation of processing power is critical to battery life and the sustained operation of autonomous robots, FoVI3D has been investigating an alternative to ROS to improve battery longevity/performance and reduce the complexity of autonomous systems.  However, the CRO MK1 Rover has the flexibility and capability to run either ROS or CRos depending on the use case.   
