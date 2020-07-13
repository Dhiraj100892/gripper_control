# Install dependencies
```buildoutcfg
sudo apt-get install ros-kinetic-dynamixel-workbench 
sudo apt-get install ros-kinetic-dynamixel-workbench-msgs
```

# Copy Udev rules
```buildoutcfg
sudo cp udev_rules/*.rules /etc/udev/rules.d
sudo service udev reload
sudo service udev restart
sudo udevadm trigger
sudo usermod -a -G dialout $USER
```

#Build Repository
```buildoutcfg
catkin_make
```

#Launch Dynamixel
```buildoutcfg
source PATH_TO_REPO/devel/setup.bash
locobot_control dynamixel_controllers.launch dxl_baud_rate:=BUAD_RATE
```

#Update Constants
[Refer to Gripper constants](https://github.com/Dhiraj100892/gripper_control/blob/master/src/locobot_control/include/locobot_control/locobot_controller.h#L69-L73)

# How to use it
[Refer to code](./src/locobot_control/scripts/locobot_control/gripper.py)