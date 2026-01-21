# Galaxea R1 Lite Description

This package contains the description files for Galaxea R1 Humanoid Robot. The origin models could be found
at [GalaxeaManipSim](https://github.com/OpenGalaxea/GalaxeaManipSim).

![Isaac](../../.images/galaxea_r1_lite_isaac.png)

## 1. Build

```bash
cd ~/ros2_ws
colcon build --packages-up-to galaxea_r1lite_description --symlink-install
```

## 2. Visualize
### 2.1 Full Robot

* R1 Lite with A1X Arm
```bash
source ~/ros2_ws/install/setup.bash
ros2 launch robot_common_launch manipulator.launch.py robot:=galaxea_r1lite
```

![A1X](../../.images/galaxea_r1lite_x.png)
* R1 Lite with A1Y Arm
```bash
source ~/ros2_ws/install/setup.bash
ros2 launch robot_common_launch manipulator.launch.py robot:=galaxea_r1lite type:=y
```

![A1Y](../../.images/galaxea_r1lite_y.png)

### 2.2 Components
* Base
  ```bash
  source ~/ros2_ws/install/setup.bash
  ros2 launch robot_common_launch component.launch.py robot:=galaxea_r1lite
  ```
* A1X with Camera
  ```bash
  source ~/ros2_ws/install/setup.bash
  ros2 launch robot_common_launch component.launch.py robot:=galaxea_r1lite type:=a1x
  ```
* A1Y with Camera
  ```bash
  source ~/ros2_ws/install/setup.bash
  ros2 launch robot_common_launch component.launch.py robot:=galaxea_r1lite type:=a1y
  ```

## 3. OCS2 Demo

### 3.1 Official OCS2 Mobile Manipulator Demo

* With R1X
    ```bash
    source ~/ros2_ws/install/setup.bash
    ros2 launch robot_common_launch manipulator_ocs2.launch.py robot_name:=galaxea_r1lite
    ```
* With R1Y
    ```bash
    source ~/ros2_ws/install/setup.bash
    ros2 launch robot_common_launch manipulator_ocs2.launch.py robot_name:=galaxea_r1lite type:=y
    ```

### 3.2 OCS2 Arm Controller Demo

#### 3.2.1 Mock Components
```bash
source ~/ros2_ws/install/setup.bash
ros2 launch ocs2_arm_controller demo.launch.py robot:=galaxea_r1lite
```

```bash
source ~/ros2_ws/install/setup.bash
ros2 launch ocs2_arm_controller demo.launch.py robot:=galaxea_r1lite hardware:=gz
```

#### 3.2.2 Isaac Sim
```bash
source ~/ros2_ws/install/setup.bash
ros2 launch ocs2_arm_controller demo.launch.py robot:=galaxea_r1lite hardware:=isaac
```