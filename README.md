# Image Acquisition using Web Camera
# Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.  
i) Write the frame as JPG  
ii) Display the video  
iii) Display the video by resizing the window  
iv) Rotate and display the video  

# Software Used
Anaconda - Python 3.7
# Algorithm
## Step 1:
Use cv2.VideoCapture(0) to access web camera.

## Step 2:
Use cv2.imread to read the video or image.

## Step 3:
Use cv2.imwrite to save the image.

## Step 4:
Use cv2.imshow to show the video.

## Step 5:
End the program and close the output video window.

# Program
### Developed By: Gnanendran N  
### Register No: 212223240037

## i) Write the frame as JPG file

```py
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

## ii) Display the video

```py
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


## iii) Display the video by resizing the window
```py
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



## iv) Rotate and display the video
```py
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
<img width="645" height="461" alt="image" src="https://github.com/user-attachments/assets/e8ce05a3-8bda-472f-8e4b-3a936a2c248b" />

### ii) Display the video
<img width="681" height="436" alt="image" src="https://github.com/user-attachments/assets/18fa1d49-e0c9-4bc1-916a-37669f0eb5d4" />

### iii) Display the video by resizing the window
<img width="559" height="435" alt="image" src="https://github.com/user-attachments/assets/deb7891e-a0e2-4137-86c9-067f883d06a9" />

### iv) Rotate and display the video
<img width="585" height="433" alt="image" src="https://github.com/user-attachments/assets/3e760d23-3c76-4b9c-b23a-9b625b739b3d" />

## Result:
Thus the image is accessed from webcamera and displayed using openCV.




