# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program


____________________________  

---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
```
import cv2
import matplotlib.pyplot as plt

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    plt.imshow(frame)
    plt.axis("off")
    plt.show()

cap.release()
```
<img width="1122" height="592" alt="Screenshot 2026-10-30 201019" src="https://github.com/user-attachments/assets/1af96c78-997c-4d15-8678-5ddb17b838aa" />

### ii) Display the video
Live webcam video is displayed
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
<img width="1196" height="645" alt="Screenshot 2026-10-30 201058" src="https://github.com/user-attachments/assets/671790cf-d643-453c-a127-826c94a4bef8" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    
    resized_frame = cv2.resize(frame, (640, 480))

    
    resized_frame = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(resized_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
<img width="1292" height="528" alt="Screenshot 2026-10-30 201135" src="https://github.com/user-attachments/assets/df491f6d-1782-4403-881c-0cac00c49d9d" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    
    rotated_frame = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(rotated_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
<img width="1356" height="560" alt="Screenshot 2026-10-30 201215" src="https://github.com/user-attachments/assets/7f676467-7e6d-4e8a-81fb-8f59d4a35f56" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
