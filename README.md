# Vins-Fusion-Jackal

This repo is for running vins-fusion using realsense d435i input. (MIT ACL)

Run the following commands:

```
roscore
```

Launch RVIZ:

```
roslaunch vins vins_rviz.launch
```

Run the Vins Node. It expects as an argument the path to the configuration file acl_vins_rishi.yaml. Replace the path shown with the actual path to the file

```
rosrun vins vins_node /home/swarm/catkin_ws/src/Vins-Fusion-Jackal/acl_vins_rishi.yaml
```

By default, this configuration file runs vins-mono (worked better than using both images), and expects the following data from the following topics:
imu topic: "/camera_d435i/imu"
image topic: "/camera_d435i/infra1/image_rect_raw"

The vins node should now output that it is waiting for data. 


Finally, play a bag file to feed vins the input it needs:

```
rosbag play 2019-10-02-10-22-58.bag 
```

Make sure the bag file is ouputting to the above topics that vins uses. The output path of Vins Fusion should show up in green in rviz.
