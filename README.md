# HAND-GESTURE-CONTROLLED-ROBOT
This project is about controlling robot motion with hand gestures which have commands like rotate, move forward and backward, accelarate and stop.The project have two parts arrow_right

- Detection of Hand_Gesture using opencv library.
- Integrating Hand_Gesture to publish commands to robot.
## DEPENDENCIES/PACKAGES
- Image processing library opencv
- ROS(Robot operating system , version-noetic)
- Gazebo (if not installed along with ROS)
## pakages :-
- ros_controll {To be cloned in catkin_ws}
- Join_state_controller (if not included in ros_controll) {To be cloned in src folder of catkin_ws}
- Turtlebot3 pakage - (https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#gazebo-simulation) {To be cloned in src folder of catkin_ws}
## ALGORITHM
### ALGORITHM FOR DETECTION OF HAND_GESTURE
Seperate out the skin color from the input frame using HSV or other color format with upper and lower bound for skin color as per range. Removal of noise from image via Morphological Transformation, and applying filters to smooothen the image.Finding the contour of the mask and finding its convex-hull.
Using the various properties for seperation various Hand_Gestures(In this project we will use Indian-sign-language as Hand_Gesture- 1,2,3..) like- convexity defects along with contour properties like solidity, extent and aspect ratio of respective gesture.
### ALGORITHM FOR ROBOT
For this project we used ROS noetic, turtlesim and turtlebot3.

-We used gazebo for simulation.
-We used ros-topic /cmd_vel for publishing velocity message to robot in gazebo simulation.
### INTEGRATION
Finally we publish angular and linear velocity as per motion we want on specific Hand_Gesture.

### HOW TO RUN THE CODE
- git clone https://github.com/ash-S26/Hand_Gesture_Controlled_Robot.git
- export TURTLEBOT3_MODEL=burger {as per requirement burger/waffle/empty}
- roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch
- python3 Hand_Gestur_Controlled_Robot.py {Finally run the code by navigating to directory where you cloned and then to where is code Hand_Gestur_Controlled_Robot.py}
- Or you can run code from any code editor.

## RESULTS
- HAND_GESTURE_DETECTION :-

hand_detection.gif

- CONTROLLING ROBOT IN EMPTY WORLD WITH HAND :-

hand_gesture_control_robot_empty_world.gif

- CONTROLLING ROBOT IN WAFFLE WORLD WITH HAND :-

hand_gesture_control_robot_waffle_world.gif
