# hand-gesture-controlled-robot
CV project to control motion of a robot by hand gestures

In this project we design code to control the motion of a turtle-bot with different hand gestures. The robot will move forward, backward, rotate left or right ,accelerate and stop according to the hand signs the user shows.
The project has two parts:
1. Code for detecting hand gestures (using openCV library).
2. Integrating hand gesture detection to publishing motion commands to the robot.

# dependencies/packages
- Ubuntu Operating system
- OpenCV library for image processing
- ROS-noetic (Robot operating system)
- Gazebo
- Pakages (clone in catkin_ws/src)
    - ros control (https://wiki.ros.org/ros_control)
    - turtlebot3 (https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#gazebo-simulation )

# results

https://user-images.githubusercontent.com/88196192/136833775-a2c4f5da-c484-49b4-b289-64e33e480ac2.mp4

https://user-images.githubusercontent.com/88196192/136834141-bf9fc7ff-a33e-4d22-8e98-2642f9faa8d1.mp4
