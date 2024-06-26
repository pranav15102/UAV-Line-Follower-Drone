# UAV-Line-Follower-Drone
This repository presents a line follower algorithm developed for the Parrot mini drone. The drone can follow a red line with a landing circle at the end autonomously thanks to an algorithm that was created using Simulink MATLAB. The drone's camera picks up the red line and circle, and the algorithm determines what control inputs are needed to keep the drone moving in the right direction.

# Line Follower Algorithm Overview
The line follower algorithm consists of two main components:
1. Line Detection and Heading Calculation: The Canny filter is used to process the live image captured by the drone's camera in order to identify edges. The program retrieves the red line's borders using the Hough line transform. Since the Hough line transform frequently yields more than one line, we take the two most noticeable lines and find the mean of their locations. An estimate of the drone's heading is given by this average coordinate, which is represented as a line that falls in the center of the red line. But because of the scant information in the first two lines, this method would not work well in some situations, such approaching a turn. The blue line may sometimes produce two directions that are 180° apart, confusing the algorithm concerning the heading. The algorithm uses additional methods to overcome this constraint.
2. Bitmap-based Approach for Heading Adjustment: In this method, the red line bitmap is used by the algorithm to process images. At the center of the image, two triangle-shaped areas of interest (ROIs) are formed, with their orientations established by the heading information that was previously obtained. The algorithm determines the value that helps determine the next heading by computing the intersection between the ROIs and the bitmap of the red line. Furthermore, by averaging the bitmaps of the red line and the ROI intersection, the method creates two X-marks. These X-marks aid in maintaining a constant heading and improving flying stability.
There is also a landing feature in the algorithm. To discover the landing circle's center, it makes use of the imfindcircles() function from MATLAB's Computer Vision Toolbox. When the circle's center is inside the designated ROI, the drone starts the landing procedure. By ensuring that the drone only lands when it reaches the desired location, this check helps to avoid making pointless landing decisions.

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
