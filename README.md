# ur12_lidar_driver

## Description
The `ur12_lidar_driver` package is a linux ROS driver for the LD-06/19 series of lidars.
The package is tested on Ubuntu 20.04 with ROS Noetic.

## Compling

This is a catkin package. Make sure the package is on `ROS_PACKAGE_PATH` after cloning the package to your workspace. And the normal procedure for compling a catkin package will work.

Make sure to install deps first:

    cd your_work_space/src
    git clone https://github.com/UbiquityRobotics/ur50_lidar.git

    cd..
    rosdep install --from-paths src --ignore-src --rosdistro=$ROS_DISTRO -y
    catkin_make 
    ```

## Parameters

The ldlidar node supports the following parameters:

* `serial_port` used to override the autodetect and select a specific port
* `lidar_frame` used to override the defauld `lidar_frame` frame_id for the 
  `sensor_msgs/laserscan` topic generated by this node.

An example launch file including all parameters is provided below:

```xml
<launch>
    <node name="ur12_lidar" pkg="ur12_lidar" type="ur12_lidar" args="LD06" output="screen" >
        <param name="serial_port" value="/dev/ttyUSB0"/>
        <param name="lidar_frame" value="laser"/>
     </node>
</launch>
```

## ROS Support

- Kinetic
- Melodic
- Noetic
