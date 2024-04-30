# liorf_localization (ros2)
 This repo is a simple location system based on a priori map, which is based on the lio-sam framework. The current version only supports small scene maps, large scene maps may have some problems.

------------------- Update Date: 2022-11-20 -------------------
- First verison

------------------- Update Date: 2022-12-13 -------------------
- Re-derivation the LM optimization, don't need coordinate transformation.

------------------- Update Date: 2023-03-18 -------------------
- Fixed a bug and was more robust for large scene maps.

------------------- Update Date: 2024-04-30 -------------------
- Add [liorf-localization ROS2](https://github.com/YJZLuckyBoy/liorf_localization/tree/liorf_localization-ros2) version (Foxy、Galactic).
 <!-- Video: [基于LIO-SAM框架SLAM算法开发（三）：定位之小场景定位算法](https://www.bilibili.com/video/BV118411L7qm/?share_source=copy_web&vd_source=dee7afd16d8b7115a533915be5690f55) -->

## Prepare priori map
  - You can get a priori map by running [liorf](https://github.com/YJZLuckyBoy/liorf) or [lviorf](https://github.com/YJZLuckyBoy/lviorf) or [liorf-ros2](https://github.com/YJZLuckyBoy/liorf/tree/liorf-ros2) or any open source SLAM algorithm(e.g. A-LOAM or LOAM or LIO-SAM);
<br>
  - Make sure the priori map name is "GlobalMap.pcd";
<br>
  - Change the "savePCDDirectory" parameter in "localization.yaml" to your priori map path.

## Dependency
- [gtsam](https://gtsam.org/get_started/)(Georgia Tech Smoothing and Mapping library)
  ```
    sudo add-apt-repository ppa:borglab/gtsam-release-4.0
    sudo apt install libgtsam-dev libgtsam-unstable-dev
  ```

## Install
1. Use the following commands to download and compile the package.
  ```
    mkdir -p ~/liorf_localization-ros2/src && cd ~/liorf_localization-ros2/src
    git clone https://github.com/YJZLuckyBoy/liorf_localization.git
    cd liorf_localization && git checkout liorf_localization-ros2
    cd ../../
    colcon build
  ```

## How to use
1. Run the launch file
  ```
    source install/setup.bash
    ros2 launch liorf_localization run_localization.launch.py
  ```

2. Use "2D Pose Estimate" on rviz to set the initial pose

3. Play bag files
  ```
    ros2 bag play 2020-03-14-16-45-35/
  ```

## Examples
  <!-- 1. Urban
  <p align='center'>
      <img src="https://github.com/YJZLuckyBoy/pic/blob/master/liorf_localization/Urban/urban.gif" alt="drawing" width="800" height = "400"/>
  </p>

## Scalable Examples
  1. Building(Avia)
  <p align='center'>
      <img src="https://github.com/YJZLuckyBoy/pic/blob/master/liorf_localization/Avia/building.gif" alt="drawing" width="800" height = "400"/>
  </p>

  2. Underground Parking(Avia)
  <p align='center'>
      <img src="https://github.com/YJZLuckyBoy/pic/blob/master/liorf_localization/Avia/underground_parking.gif" alt="drawing" width="800" height = "400"/>
  </p> -->

## Acknowledgments
  Thanks for [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM), [MulRan](https://sites.google.com/view/mulran-pr/) and [UrbanNavDataset](https://github.com/weisongwen/UrbanNavDataset).