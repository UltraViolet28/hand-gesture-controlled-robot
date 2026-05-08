# Hand Gesture Controlled Robot

Real-time Indian Sign Language (ISL) digit gesture recognition that maps hand poses to motion commands on a TurtleBot3, using only a standard webcam.

## Overview

This project implements a vision-based human-robot interaction system. A webcam detects hand gestures corresponding to ISL digit signs (0–9) using classical image processing — no pretrained neural network. Detected gestures are mapped to velocity commands (forward, backward, rotate left/right, stop, accelerate) published over ROS to a TurtleBot3. The system was tested in Gazebo simulation and on a real TurtleBot3. This was the first robotics project completed at IvLabs.

## Methods / Approach

- **Color segmentation:** YCrCb color space with fixed skin-tone bounds; HSV [0,58,30]–[33,255,255] for skin region extraction
- **Preprocessing:** morphological dilation (4 iterations) + erosion (2 iterations) + closing + median blur to isolate hand region
- **Feature extraction:** contour finding, convex hull, convexity defects, cosine rule for inter-finger angles
- **Classification:** rule-based on convexity defect count, solidity, extent, and aspect ratio — no learned model
- **Robot control:** ROS Noetic, Twist messages published to `/cmd_vel` at 10 Hz
- **Platform:** TurtleBot3 (Gazebo simulation + real hardware)
- **Libraries:** OpenCV (cv2), NumPy, rospy

## Results

Demonstration videos are in `results/`:
- `Hand_Gesture_detection.mp4` — gesture detection pipeline running on webcam feed
- `Hand_Gesture_controlled_bot.mp4` — robot control in Gazebo waffle world
- `Hand_Gesture_controlled_bot_short.mp4` — shortened demo
- `Hand_gesture.mp4` — gesture recognition footage

The system reliably distinguishes gestures 0–5 under controlled lighting. Performance degrades under varying illumination due to fixed HSV thresholds.

## How to Run

Dependencies:
- ROS Noetic
- TurtleBot3 packages: https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#gazebo-simulation
- `ros_control`, `joint_state_controller` (clone into catkin workspace src/)
- Python: `pip install opencv-python numpy`

```bash
export TURTLEBOT3_MODEL=waffle   # or burger / empty
roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch
# In a separate terminal, from the code/ directory:
python3 turtle_hand.py
```

For gesture detection only (no ROS):
```bash
python3 code/sign_lang_detection_final.py
```

## Context

Developed at IvLabs, VNIT Nagpur, June 2022. First IvLabs robotics project.
