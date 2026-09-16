
## FAST-LIO 2.0 

## Quickly Run with Zvision_Series

**For ROS2 Users**: Please switch to the **ros2** branch and follow the instructions at [ros2 branch (main) ](https://github.com/ZVISION-lidar/FAST_LIO2_ZVISION.git)

## 1. Prerequisites
### 1.1 **Ubuntu** and **ROS**
**Ubuntu >= 18.04**

The **default from apt** PCL and Eigen is enough for FAST-LIO to work normally.

ROS >= melodic (Recommend to use ROS-Noetic). 

### 1.2. **PCL && Eigen**
PCL    >= 1.8,   Follow [PCL Installation](https://pointclouds.org/downloads/#linux).

Eigen  >= 3.3.4, Follow [Eigen Installation](http://eigen.tuxfamily.org/index.php?title=Main_Page).


## 2. Build
Clone the repository and colcon build:

```bash
    cd <ros1_ws>/src # cd into a ros1 workspace folder
    git clone -b ROS1 https://github.com/ZVISION-lidar/FAST_LIO_ZVISION.git
    git pull
    cd ..
    catkin_make
```


## 3. Directly run with zvision

### 3.1 Run use ros launch

Launch zvision ros driver.

```bash
cd <yourself_zvision_ros_driver_ws>
source devel/setup.bash # use setup.zsh if use zsh
roslaunch zvlidar_sdk run.launch
```


Launch fastlio2.
```bash
cd <ros1_ws>
source devel/setup.bash # use setup.zsh if use zsh
roslaunch fast_lio mapping_zvision_nz1.launch # depend on yourself lidar model: roslaunch fast_lio mapping_zvision_nz*(1/3/5/5_mt).launch.py 
```


### 3.2 PCD file save

Enable `pcd_save.pcd_save_en` in the config file and set the `map_file_path` to the path where the map will be saved.

```pcl_viewer scans.pcd``` can visualize the point clouds.
