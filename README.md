## VINS-RGBD for [OpenLORIS-Dataset](https://lifelong-robotic-vision.github.io/dataset/scene)
Based on the open source SLAM frameworks [VINS-Mono](https://github.com/HKUST-Aerial-Robotics/VINS-Mono) and [VINS-RGBD](https://github.com/STAR-Center/VINS-RGBD), you can download the OpenLoris Datasets and test it in the VINS-RGBD.

## How to run

Ubuntu 16.04 & 18.04

ROS Kinetic or Melodic

Ceres-Solver

Sophus

```
mkdir -p catkin_ws/src
cd catkin_ws/src
git clone https://github.com/LeonGoretzkatju/IndoorSLAM_VINS_RGBD
cd ..
catkin_make
//Open one terminal
roscore

//Open one terminal
roslaunch vins_estimator vins_rviz.launch

//Open one terminal and go to the vins_estimator/launch folder 
roslaunch openloris.launch

//Open one terminal 
rosbag play xxx.bag
```



## RGBD-Inertial Trajectory Estimation and Mapping for Small Ground Rescue Robot
Based one open source SLAM framework [VINS-Mono](https://github.com/HKUST-Aerial-Robotics/VINS-Mono).

The approach contains
+ Depth-integrated visual-inertial initialization process.
+ Visual-inertial odometry by utilizing depth information while avoiding the limitation is working for 3D pose estimation.
+ Noise elimination map which is suitable for path planning and navigation.

However, the proposed approach can also be applied to other application like handheld and wheeled robot.

This dataset is part of the dataset collection of the [STAR Center](https://star-center.shanghaitech.edu.cn/), [ShanghaiTech University](http://www.shanghaitech.edu.cn/eng): https://star-datasets.github.io/

A video showing the data is available here: https://robotics.shanghaitech.edu.cn/datasets/VINS-RGBD

## Paper
Shan, Zeyong, Ruijian Li, and Sören Schwertfeger. "RGBD-inertial trajectory estimation and mapping for ground robots." Sensors 19.10 (2019): 2251.


    @article{shan2019rgbd,
      title={RGBD-inertial trajectory estimation and mapping for ground robots},
      author={Shan, Zeyong and Li, Ruijian and Schwertfeger, S{\"o}ren},
      journal={Sensors},
      volume={19},
      number={10},
      pages={2251},
      year={2019},
      publisher={Multidisciplinary Digital Publishing Institute}
    }


## 1. Prerequisites
1.1. **Ubuntu** 16.04 or 18.04.

1.2. **ROS** version Kinetic or Melodic fully installation

1.3. **Ceres Solver**
Follow [Ceres Installation](http://ceres-solver.org/installation.html)

1.4. **Sophus**
```
  git clone http://github.com/strasdat/Sophus.git
  git checkout a621ff
```


## 2. Datasets
Recording by RealSense D435i. Contain 9 bags in three different applicaions:
+ [Handheld](https://star-center.shanghaitech.edu.cn/seafile/d/0ea45d1878914077ade5/)
+ [Wheeled robot](https://star-center.shanghaitech.edu.cn/seafile/d/78c0375114854774b521/) ([Jackal](https://www.clearpathrobotics.com/jackal-small-unmanned-ground-vehicle/))
+ [Tracked robot](https://star-center.shanghaitech.edu.cn/seafile/d/f611fc44df0c4b3d936d/)

Note the rosbags are in compressed format. Use "rosbag decompress" to decompress.

Topics:
+ depth topic: /camera/aligned_depth_to_color/image_raw
+ color topic: /camera/color/image_raw
+ imu topic: /camera/imu




## 3. Licence
The source code is released under [GPLv3](http://www.gnu.org/licenses/) license.
