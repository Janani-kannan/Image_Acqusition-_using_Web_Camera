
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

### Developed By: Janani K
### Register No: 212224230102


## Algorithm

Step 1: Use cv2.VideoCapture(0) to access web camera

Step 2: Use cv2.imread to read the video or image Step 3: Use cv2.imwrite to save the image

Step 4: Use cv2.imshow to show the video

Step 5: End the program and close the output video window by pressing 'q'.

## Program:

i) WRITE THE FRAME AS JPG FILE 
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
ii) DISPLAT THE VIDEO
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
iii) DISPLAY THE VIDEO BY RESIZING THE WINDOW 
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
iv) ROTATE AND DISPLAY THE VIDEO 
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## Output

### i) Write the frame as JPG image

<img width="652" height="542" alt="image" src="https://github.com/user-attachments/assets/666f27f1-e046-472d-b57a-8316423f37cd" />

### ii) Display the video

<img width="653" height="507" alt="image" src="https://github.com/user-attachments/assets/7ef4c87c-b387-436e-9ec9-4055bbd50c84" />


### iii) Display the video by resizing the window

<img width="332" height="492" alt="image" src="https://github.com/user-attachments/assets/b7f112f5-bc5c-4794-b9f8-111e3a7613f6" />


### iv) Rotate and display the video

<img width="371" height="507" alt="image" src="https://github.com/user-attachments/assets/a70ca00a-ec0b-490c-acbb-0266067e11bb" />

## RESULT

Thus the image is accessed from webcamera and displayed using openCV.



