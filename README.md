# Testing Turtlesim in ROS

## 1 - Run master node
```bash
roscore
```
![Run master node](https://i.imgur.com/5Qumy2w.png)

## 2 - Run turtlesim_node
```bash
rosrun turtlesim turtlesim_node
```
![Run turtlesim_node 1](https://i.imgur.com/MQm3GJP.png)
![Run turtlesim_node 2](https://i.imgur.com/Es9gbox.png)

## 3 - Using keyboard to move the turtle
This will open a listener for the keyboard
```bash
rosrun turtlesim turtle_teleop_key
```
![Using keyboard to move the turtle](https://i.imgur.com/F5VaByi.png)

We can see two nodes and the topic `command_velocity`. The `teleop_turtle` node is the publisher and `turtlesim` is the subscriber.

You can also see live data for the location of the turtle and the change when we move it using the keyboard
```bash
rostopic echo /turtle1/cmd_vel
```
![Live data for turtle location](https://i.imgur.com/uuCjO11.png)

## 4 - Publishing data directly to change the location of the turtle
```bash
rostopic pub -1 /turtle1/cmd_vel geometry_msgs/Twist -- '[3, 4, 1]' '[0.0, 0.0, 1.5]'
```
![Publishing data directly](https://i.imgur.com/UFBjL6b.png)

