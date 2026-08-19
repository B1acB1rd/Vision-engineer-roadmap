# Autonomous Vision Engineer Roadmap

A project-first roadmap for learning computer vision, robotics perception, mapping, planning, and autonomous systems using only a phone, a laptop, and a growing set of practical projects.

> Built for people who want to learn by shipping real systems instead of memorizing theory first.

## Why this roadmap exists

Most computer vision roadmaps are too academic and too slow. This one is designed around the actual pipeline used in robotics and autonomy:

- See the world with a camera
- Understand what is in the scene
- Estimate motion and position
- Build a map of the world
- Plan a route
- Control a robot or vehicle to act on that plan

The roadmap starts with the sensor you already have: your phone camera.

## Learning philosophy

- Start with the sensor, not the theory
- Build projects that run on a laptop or phone
- Read math only when a project blocks progress
- Focus on systems that output something real
- Keep a portfolio of working demos

---

## At a glance

| Stage | Focus | Typical duration | Goal |
| --- | --- | --- | --- |
| 1 | See | 6–8 weeks | Camera geometry, pipelines, and basic perception |
| 2 | Perceive | 6–8 weeks | Depth, motion, segmentation, and tracking |
| 3 | Locate | 8–10 weeks | Visual odometry, SLAM, and sensor fusion |
| 4 | Map | 6–8 weeks | Occupancy grids, 3D reconstruction, and neural maps |
| 5 | Plan | 8–10 weeks | Path planning and autonomous control |
| 6 | Full system | 12–16 weeks | End-to-end autonomous stack and capstone project |

---

## Stage 1 — See

Focus: camera geometry, image processing, and building a reliable sensor pipeline.

### Projects

1. Phone as a computer vision sensor
   - Stream live camera feed from your phone to your laptop
   - Process frames with OpenCV
   - Save video and build a reusable pipeline

2. Calibrate your phone camera
   - Use a chessboard pattern
   - Estimate intrinsics and distortion coefficients
   - Undistort an image and understand camera models

3. Homography for flat-surface mapping
   - Correct perspective distortion
   - Build bird's-eye-view transforms
   - Understand projective geometry in practice

4. Feature matching between two views
   - Detect and match keypoints across images
   - Recover relative camera motion
   - Learn the foundation of visual odometry and SLAM

5. Vanishing point detection
   - Detect lane and corridor geometry
   - Learn why parallel lines converge in perspective images

### Exit criteria

- You can stream camera data from a phone to Python
- You can calibrate a camera and use the intrinsic matrix
- You can detect features between two views and estimate relative motion
- You understand why perspective transforms and vanishing points matter

---

## Stage 2 — Perceive

Focus: depth, motion, object recognition, and scene understanding.

### Projects

1. Real-time depth on your phone feed
   - Run monocular depth estimation on live video
   - Visualize depth as a heatmap
   - Use the depth map to estimate object distance

2. Optical flow and motion estimation
   - Detect movement between frames
   - Estimate direction and motion magnitude
   - Understand ego-motion and obstacle movement

3. Semantic segmentation on driving video
   - Use a pretrained model such as SegFormer
   - Label road, vehicles, pedestrians, sky, buildings, and more
   - Build a basic scene understanding pipeline

4. Multi-object tracking
   - Detect multiple objects and assign persistent IDs
   - Track pedestrians and vehicles over time
   - Build motion trajectories

5. Full perception stack
   - Combine depth, segmentation, detection, and tracking
   - Run a multi-component live pipeline on your phone feed
   - Create a real portfolio demo

### Exit criteria

- You can estimate depth from camera data
- You can track objects over time
- You understand the difference between segmentation, detection, and tracking
- You can show a live perception pipeline working on a real video stream

---

## Stage 3 — Locate

Focus: position estimation, mapping, motion models, and localisation.

### Projects

1. Visual odometry from video
   - Estimate the camera's movement between frames
   - Recover translation and rotation
   - Plot the trajectory of a moving phone

2. ORB-SLAM3 room mapping
   - Build a sparse 3D point cloud map of a room
   - Run a real SLAM system on a recorded video sequence
   - Observe loop closure and map correction

3. Kalman filter from scratch
   - Implement the predict/update equations yourself
   - Smooth noisy sensor measurements
   - Learn the core of state estimation

4. Phone IMU + camera fusion
   - Combine accelerometer and gyroscope data with vision
   - Build a basic visual-inertial odometry pipeline
   - Learn why sensor fusion is needed

### Exit criteria

- You can estimate pose changes from visual data
- You understand why odometry drifts over time
- You can explain loop closure and map correction
- You have built a real localisation system and seen it work in practice

---

## Stage 4 — Map

Focus: turning sensor data into useful world representations.

### Projects

1. Occupancy grid from a room map
   - Convert a 3D point cloud into a 2D navigable map
   - Mark free space and obstacles
   - Build a map used by robots

2. COLMAP for 3D reconstruction
   - Recover geometry from a set of phone photos
   - Build sparse and dense reconstructions of a place
   - Learn the structure-from-motion pipeline

3. NeRF from phone photos
   - Train a neural scene representation from captured images
   - Render novel views from new camera angles
   - Learn how neural mapping works

4. Semantic map
   - Project segmentation labels into 3D space
   - Label points and objects in the world
   - Connect perception to robot understanding

### Exit criteria

- You can build a map that supports navigation
- You understand the difference between sparse reconstruction and dense geometry
- You have seen both classical and neural mapping approaches

---

## Stage 5 — Plan

Focus: path planning, simulation, and control.

### Projects

1. A* path planner on your room map
   - Find a path from start to goal while avoiding obstacles
   - Visualize the search and final route

2. First robot in PyBullet
   - Load a robot model in simulation
   - Drive it using wheel commands and control inputs

3. Vision-guided robot in simulation
   - Give the robot a camera and feed it through the perception pipeline
   - Use depth and planning to drive autonomously

4. CARLA self-driving demo
   - Spawn a vehicle in simulation
   - Drive it with camera-based control
   - Learn how lane following and autonomous driving logic are built

5. Imitation learning driver
   - Collect expert-driving data
   - Train a neural network to predict controls from camera frames
   - Re-deploy it in simulation

### Exit criteria

- You can plan around obstacles
- You can control a robot or vehicle in simulation
- You have a working autonomous navigation loop
- You can show a portfolio video of a robot driving itself

---

## Stage 6 — Full system

Focus: integration, research, deployment, and portfolio quality.

### Projects

1. RRT* for complex planning problems
2. 3D Gaussian splatting for real-time neural mapping
3. Language-commanded robot
4. Reproduce a research paper from scratch

### Final capstone

Build a camera-only autonomous navigator in CARLA or simulation that can:

- perceive the scene from camera input only
- localize itself without GPS
- build or update a map
- plan around obstacles
- execute a route with control logic
- recover gracefully when a module fails

This is the project that should sit at the centre of your portfolio.

---

## Recommended stack

### Core tools

- Python
- OpenCV
- NumPy
- PyTorch
- Matplotlib
- Jupyter notebooks

### Robotics and simulation

- PyBullet
- CARLA
- ORB-SLAM3
- Open3D
- COLMAP

### Research and model workflows

- Hugging Face Transformers
- Kaggle GPUs
- Weights & Biases
- ROS2 for realistic robotics deployment

---

## How to use this roadmap

1. Start at Stage 1 and complete the projects in order.
2. Keep a short project log and a demo video for each one.
3. Do not jump ahead just because a concept looks interesting.
4. Read the math reference only when a project is blocking you.
5. Treat each stage as a system-building milestone, not just a checklist of tutorials.

---

## Useful references

- Multiple View Geometry in Computer Vision — Hartley & Zisserman
- Probabilistic Robotics — Thrun, Burgard, and Fox
- Planning Algorithms — Steven M. LaValle
- State Estimation for Robotics — Timothy D. Barfoot
- End to End Learning for Self-Driving Cars — Bojarski et al.

---

## Expected outcome

By the time you finish this roadmap, you should be able to:

- build a camera pipeline from a phone or webcam
- estimate depth, motion, and scene structure
- build a map of a real environment
- plan a route and drive a robot or vehicle through it
- explain the engineering decisions behind autonomous systems
- have multiple portfolio projects that demonstrate real capability

---

## Final note

This roadmap is intentionally practical. The goal is not to read everything first. The goal is to build systems that work, learn the missing theory when needed, and turn those systems into strong engineering demos.

If you want, I can also turn this into:

- a more premium landing-page version with badges and separators,
- a shorter website-friendly introduction section,
- or a version with a table of contents and cleaner GitHub markdown styling.
