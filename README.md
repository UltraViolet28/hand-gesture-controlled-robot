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
- git clone https://github.com/UltraViolet28/hand-gesture-controlled-robot.git
- export TURTLEBOT3_MODEL=burger {as per requirement burger/waffle/empty}
- roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch
- python3 turtle_hand.py {Finally run the code by navigating to directory where you cloned and then to where is code Hand_Gestur_Controlled_Robot.py}
- Or you can run code from any code editor.

## RESULTS
- HAND_GESTURE_DETECTION :-

![image](https://user-images.githubusercontent.com/88196192/172039668-3b382d9f-9372-4dcc-827a-d7e48cfa847d.png)

- CONTROLLING ROBOT IN EMPTY WORLD WITH HAND :-

![image](https://user-images.githubusercontent.com/88196192/172039684-40f2b8c3-c855-4d8a-b355-3fb692707d62.png)
- CONTROLLING ROBOT IN WAFFLE WORLD WITH HAND :-

![image](https://user-images.githubusercontent.com/88196192/172039692-9ecfbe4e-21b0-47f7-ba88-c482eb56874d.png)
