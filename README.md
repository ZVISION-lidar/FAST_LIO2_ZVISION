
## FAST-LIO2.0

FAST-LIO2.0 With ZVISION LIDAR 

<div align="center">
  <img src="doc/fastlio2_zvsion_nz5mt_demo.gif" width="100%">
</div>


## Quickly Run with Zvision_1/3/5/5_MT

**For ROS1 Users**: Please switch to the **ros1** branch and follow the instructions at [ros1 branch](https://github.com/ZVISION-lidar/FAST_LIO_ZVISION/tree/ROS1)

## 1. Prerequisites
### 1.1 **Ubuntu** and **ROS**
**Ubuntu >= 22.04**

The **default from apt** PCL and Eigen is enough for FAST-LIO to work normally.

ROS >= Foxy (Recommend to use ROS-Humble). [ROS Installation](https://docs.ros.org/en/humble/Installation.html)


### 1.2. **PCL && Eigen**
PCL    >= 1.8,   Follow [PCL Installation](https://pointclouds.org/downloads/#linux).

Eigen  >= 3.3.4, Follow [Eigen Installation](http://eigen.tuxfamily.org/index.php?title=Main_Page).


## 2. Build
Clone the repository and colcon build:

```bash
    cd <ros2_ws>/src # cd into a ros2 workspace folder
    git clone https://github.com/ZVISION-lidar/FAST_LIO_ZVISION.git
    cd ..
    colcon build 
```


## 3. Directly run with zvision

### 3.1 Run use ros launch

Launch zvision ros driver.

```bash
cd <yourself_zvision_ros_driver_ws>
source install/setup.bash # use setup.zsh if use zsh
ros2 launch zvlidar_sdk run.py
```


Launch fastlio2.
```bash
cd <ros2_ws>
source install/setup.bash # use setup.zsh if use zsh
ros2 launch fast_lio mapping_zvision_nz1.launch.py # depend on yourself lidar model: ros2 launch fast_lio mapping_zvision_nz*(1/3/5/5_MT).launch.py 
```


### 3.2 PCD file save

Enable `pcd_save.pcd_save_en` in the config file and set the `map_file_path` to the path where the map will be saved.

```pcl_viewer scans.pcd``` can visualize the point clouds.

