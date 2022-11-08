# Optitrack Perception Module

[![Dependency Status][Overworld-Dependency-Image]][Overworld-Dependency-Url]
[![Dependency Status][Optitrack-Dependency-Image]][Optitrack-Dependency-Url]

This package is an Overworld human perception module using the Optitrack mocap system.

We advise you to install all Overworld external perception modules in a same folder (e.g. overworld_modules) in your ROS workspace.

## Installation

Here we assume Overworld to be installed.

```bash
cd ~/catkin_ws/src
git clone https://github.com/RIS-WITH/optitrack_msgs.git
cd overworld_modules
git clone https://github.com/sarthou/optitrack_perception_module.git
cd ../..
catkin_make
```

[Overworld-Dependency-Image]: https://img.shields.io/badge/dependencies-overworld-yellowgreen
[Overworld-Dependency-Url]: https://github.com/sarthou/overworld

[Optitrack-Dependency-Image]: https://img.shields.io/badge/dependencies-optitrack_msgs-yellowgreen
[Optitrack-Dependency-Url]: https://github.com/sarthou/optitrack_msgs