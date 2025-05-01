# Vision-Based Line Follower Drone – for Warehouse Inventory Movement

## 🛠️ Problem Being Solved
Indoor environments like warehouses lack GPS, requiring visual solutions for drone navigation over marked paths.

## ✅ Solution Overview
Built a drone that uses a downward camera, OpenCV, and PID control to follow painted or taped lines autonomously in real-time.

## 🧠 Technical Details
- **Detection:** OpenCV pipeline using color masking and contours
- **Control:** Simulink-modeled PID algorithm for yaw/roll
- **Execution:** Entire system runs onboard (no ground station)
- **Testing:** Curved and occluded line segments in lab settings

## 📊 Key Results
- <200ms latency from camera to control
- Reliable path tracking and smooth navigation
- Fully vision-based control without GPS or motion trackers

## ▶️ Demo Video
[Watch on YouTube](https://youtube.com/shorts/wr_JAsBVCIU)
# Usage
To use this line follower algorithm with your Parrot mini drone, follow these steps:

1. Set up your Parrot mini drone and establish a connection with your computer.
2. Open the MATLAB project or script that contains the line follower algorithm.
3. Configure the relevant parameters, such as camera settings and ROI orientation, to match your drone setup.
4. Execute the script or run the simulation in Simulink to start the algorithm.
5. Monitor the drone's behavior as it follows the red line and lands on the designated circle.
6. Make adjustments to the algorithm or parameters as needed to improve performance based on your observations.

# Requirements
To run this line follower algorithm, you need the following:

1. Parrot mini drone
2. MATLAB with Simulink and Computer Vision Toolbox
