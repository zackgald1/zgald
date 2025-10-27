# Object Tracker

<div style="position:relative; padding-bottom:56.25%; height:0; overflow:hidden; margin-top:1em; margin-bottom:1.5em;">
  <iframe 
    src="https://www.youtube.com/embed/qia1dABN3dE" 
    title="Object Tracker Demo"
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen
    style="position:absolute; top:0; left:0; width:100%; height:100%; border-radius:12px;">
  </iframe>
</div>

<p style="text-align:center; margin-top:-1em; font-style:italic; color:gray;">
  Demonstration of real-time object tracking and PID-based motor control.
</p>

---

## Summary

This project combines computer vision and embedded motor control to track a red object in real time using a camera and a microcontroller. The Python script identifies the target through HSV color segmentation and applies a PID controller to keep the target centered in the camera frame. Control commands are sent over UART to a C-based firmware, which adjusts two PWM outputs to drive the motors accordingly.

---

## How It Works

### Vision & Control (Python)
- Uses OpenCV to capture frames and isolate red regions via HSV filtering and morphological cleaning.  
- Computes the centroid of the detected region and calculates pixel error relative to the frame center.  
- Applies a **PID controller** to generate a motor speed command based on proportional, integral, and derivative terms.  
- Implements anti-windup for integral accumulation and derivative smoothing (`d_error = 0.7 * last_d_error + 0.3 * d_error`).  
- Includes a **“search sweep”** mode to oscillate the motors if no target is found.  
- Supports real-time gain tuning from the keyboard (`u` and `d` keys adjust Kp) and auto-tuning recommendations using oscillation periods.  
- Plots error, speed, and time using live Matplotlib threads for control tuning visualization.  
:contentReference[oaicite:0]{index=0}:contentReference[oaicite:1]{index=1}

### Embedded Motor Control (C Firmware)
- Receives two UART bytes from the Python script — one for direction and one for speed.  
- Automatically handles mixed packet order (determines which byte is direction vs. speed).  
- Converts received speed into PWM periods (`Period = 4 * Clock_Speed / Motor_Speed`).  
- Writes complementary PWM signals to control left/right motor direction.  
- Displays live direction and speed on LCD for debugging.  
:contentReference[oaicite:2]{index=2}

---

## Skills I Gained

- **PID Controls:** Tuning Kp, Ki, and Kd for smooth target tracking and response stability.  
- **Computer Vision:** HSV segmentation, contour filtering, and centroid computation.  
- **Serial Communication:** Designing a UART protocol for reliable speed/direction transfer.  
- **Embedded Systems:** PWM generation, motor driver interfacing, and LCD data output.  
- **Real-Time Plotting:** Visualizing dynamic signals (error, speed, dt) for tuning feedback.  
- **Debugging & Integration:** Synchronizing two control loops (vision and motion) over serial.

---

## Technologies Used
**Languages:** Python, C  
**Libraries:** OpenCV, NumPy, Matplotlib, PySerial  
**Hardware:** Camera, Microcontroller (UART + Dual PWM), LCD module  
**Concepts:** Computer Vision · Control Systems · PID Tuning · UART Communication

---

## 🔽 Download the Code

You can view or download the full source files directly from this repository:

- [**Python Vision Control** — `camerafinalv7.py`](./camerafinalv7%20(1).py){target=_blank}
- [**Embedded Firmware** — `final456.c`](./final456%20(1).c){target=_blank}

---

*Next step:* Integrate IMU feedback or object distance measurement for full closed-loop motion stabilization.
