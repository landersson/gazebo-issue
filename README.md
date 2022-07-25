# Small Standalone Example to Reproduce a Gazebo Issue

## Dependencies

ros-galactic-desktop, ros-galactic-gazebo-ros, ros-galactic-gazebo-plugins

## Reproducing the Issue

1. `gazebo --verbose -s libgazebo_ros_factory.so world.sdf`
2. `python spawn_entity.py camera_array cam.sdf`
3. `ros2 service call /delete_entity gazebo_msgs/srv/DeleteEntity "{'name': 'camera_array'}"`
4. `python spawn_entity.py camera_array cam.sdf`

First time spawning the camera_array, it will have a camera sensor attached with visualization enabled.

Repeating steps 3-4, usually just once, will cause the camera sensor visualization to disappear.



  




