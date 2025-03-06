🔥 Fire Detection System – Project Overview
📖 Introduction
This Fire Detection System is built using Python and OpenCV to detect fire in real-time using a webcam or video feed. If fire is detected, the system triggers an alarm sound as an alert.

🚀 Features
✅ Real-Time Fire Detection – Uses OpenCV to analyze video frames for fire detection.
✅ Alarm System – Plays an alarm sound when fire is detected.
✅ Webcam & Video Feed Support – Works with live webcam input or recorded videos.
✅ Optimized Performance – Uses Gaussian Blur and HSV color filtering for accurate detection.
✅ Multi-threaded Alarm Execution – Runs the alarm sound in a separate thread for smooth performance.

🛠️ Tech Stack
Python – Core programming language.
OpenCV – For image and video processing.
NumPy – For numerical operations and mask filtering.
Playsound – To trigger an alarm sound.
Threading – To execute the alarm function separately.
📂 Project Structure
bash
Copy
Edit
/fire-detection-system
│── fire_detector.py       # Main Python script for fire detection
│── Alarm Sound.mp3        # Sound file played when fire is detected
│── README.md              # Project documentation
📌 How It Works?
Captures video feed from the webcam or a video file.
Applies Gaussian Blur & HSV filtering to detect fire color patterns.
Counts the number of red pixels in the frame.
If fire is detected, triggers an alarm sound using the playsound module.
Displays the output in a separate window.
📌 How to Run the Project?
1️⃣ Install Dependencies
bash
Copy
Edit
pip install opencv-python numpy playsound
(Ensure you have Python installed.)

2️⃣ Run the Fire Detector
bash
Copy
Edit
python fire_detector.py
(Press q to exit the application.)

📌 Code Overview
🔹 Importing Required Libraries
python
Copy
Edit
import cv2
import numpy as np
import playsound
import threading
🔹 Fire Detection Algorithm
Converts frames to HSV format.
Applies color masking for fire detection.
Counts red pixels to determine fire presence.
python
Copy
Edit
hsv = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
lower = np.array([18, 50, 50], dtype="uint8")
upper = np.array([35, 255, 255], dtype="uint8")
mask = cv2.inRange(hsv, lower, upper)
no_red = cv2.countNonZero(mask)

if int(no_red) > 15000:
    Fire_Reported += 1
🔹 Alarm System Execution
python
Copy
Edit
if Fire_Reported >= 1:
    if Alarm_Status == False:
        threading.Thread(target=play_alarm_sound_function).start()
        Alarm_Status = True

🎯 Enhancements & Future Improvements
✅ AI-Based Fire Detection – Use deep learning models for more accuracy.
✅ Email/SMS Alert System – Notify users when fire is detected.
✅ Remote Monitoring – Send real-time alerts to mobile devices.
✅ Temperature-Based Fire Detection – Integrate with thermal cameras.

📜 License
This project is open-source and free to use under the MIT License.

