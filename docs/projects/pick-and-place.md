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

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 10px; text-align: center; margin-top: 10px;">
  <div style="background-color: #1e88e5; color: white; padding: 8px; border-radius: 8px;">MATLAB Programming</div>
  <div style="background-color: #43a047; color: white; padding: 8px; border-radius: 8px;">Computer Vision</div>
  <div style="background-color: #fdd835; color: black; padding: 8px; border-radius: 8px;">Coordinate Transformations</div>
  <div style="background-color: #8e24aa; color: white; padding: 8px; border-radius: 8px;">UART Communication</div>
  <div style="background-color: #e53935; color: white; padding: 8px; border-radius: 8px;">Robotics Integration</div>
</div>

---

### 🎥 Demonstration Video

<div style="text-align:center;">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/itHWlRx7RO8"  
  title="Object Tracker Demo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"  
  allowfullscreen></iframe>
</div>


You can also [download it here](Challenge455.m).

