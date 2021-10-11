# hand-gesture-controlled-robot
CV project to control motion of a robot by hand gestures

In this project we design code to control the motion of a turtle-bot with different hand gestures. The robot will move forward, backward, rotate left or right ,accelerate and stop according to the hand signs the user shows.
The project has two parts:
1. Code for detecting hand gestures (using openCV library).
2. Integrating hand gesture detection to publishing motion commands to the robot.

# dependencies/pakages
- Ubuntu Operating system
- OpenCV library for image processing
- ROS-noetic (Robot operating system)
- Gazebo
- Pakages (clone in catkin_ws/src)
    - ros control (https://wiki.ros.org/ros_control)
    - turtlebot3 (https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#gazebo-simulation )

