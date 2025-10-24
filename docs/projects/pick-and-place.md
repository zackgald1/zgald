## Object Tracking and Robotic Control

This MATLAB program performs **background subtraction and object localization** for robotic vision control.  
After initializing a USB camera, the code captures a static background image and then detects any new object placed in the field of view.  
By subtracting the new frame from the background and applying a binary threshold, it isolates the object’s foreground pixels.

Using matrix operations, the script calculates the **object’s centroid** in pixel coordinates and converts it into **real-world millimeter coordinates** through calibration factors.  
A homogeneous transformation matrix aligns the camera frame to the robot’s base frame, giving precise **X** and **Y** coordinates for control.

Finally, the script establishes a **UART serial connection to a PSoC microcontroller**, transmitting the computed position data for real-time robotic movement.  
The code concludes with a loop that continuously sends the position variables until the connection is cleared, enabling synchronized motion between the MATLAB vision system and the robot’s actuators.

---

### 🧠 Skills Used
- **MATLAB Programming** – Image acquisition, background subtraction, and matrix calculations  
- **Computer Vision** – Object detection using grayscale thresholding and centroid finding  
- **Coordinate Transformations** – Converting pixel data to real-world coordinates using homogeneous matrices  
- **Embedded Communication** – UART data transfer to a PSoC microcontroller  
- **Robotics Integration** – Linking visual tracking to robotic control for real-time motion response

---

### 🎥 Demonstration Video
*A short demo video will be embedded here showing the camera detecting an object, plotting its position, and sending coordinates to the robotic arm for movement.*
