

```bash
ros2 topic pub /cmd_vel geometry_msgs/Twist '{linear:  {x: 145, y: 147, z: 149}, angular: {x: 152,y: 565.0,z: 110.0}}'

ros2 topic pub /alpo_joint_states/set_states sensor_msgs/msg/JointState '{header: {stamp: {sec: 0, nanosec: 0}, frame_id: ""}, name: ["alpo_front_left_wheel_steering_joint"], position: [1.0], velocity: [1.0], effort: [1.0]}'

```



ros2 topic pub /alpo_joint_states/set_states sensor_msgs/msg/JointState header:\ \ stamp:\ \ \ \ sec:\ 0\ \ \ \ nanosec:\ 0\ \ frame_id:\ \'\'name:\ ["alpo_rear_left_wheel_spinning_joint"]position:\ [1]velocity:\ [1]effort:\ [1]\ 

header:
  stamp:
    sec: 0
    nanosec: 0
  frame_id: ''
