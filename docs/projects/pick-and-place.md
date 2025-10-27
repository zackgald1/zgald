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

  <div style="background-color: #8C1D40; color: white; padding: 8px; border-radius: 8px; font-weight: bold;">
    MATLAB Programming
  </div>
  
  <div style="background-color: #FFC627; color: #000; padding: 8px; border-radius: 8px; font-weight: bold;">
    Computer Vision
  </div>
  
  <div style="background-color: #8C1D40; color: white; padding: 8px; border-radius: 8px; font-weight: bold;">
    Coordinate Transformations
  </div>
  
  <div style="background-color: #FFC627; color: #000; padding: 8px; border-radius: 8px; font-weight: bold;">
    UART Communication
  </div>
  
  <div style="background-color: #8C1D40; color: white; padding: 8px; border-radius: 8px; font-weight: bold;">
    Robotics Integration
  </div>
</div>

---

### 🎥 Demonstration Video

<div style="position:relative; padding-bottom:56.25%; height:0; overflow:hidden;">
  <iframe 
    src="https://www.youtube.com/embed/4AXSAaTqBM4" 
    title="Object Tracker Demo"
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen
    style="position:absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>



You can also [download it here](Challenge455.m).

