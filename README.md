# Record-Image-Acquisition-using-Web-Camera


## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window.

## Program:
``` 
### Developed By: Krishna Prasad S
### Register No:  212223230108
```

## i) Write the frame as JPG file
```py
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("krishna_prasad.jpg",frame)
videoCaptureObject.release()

captured_image = cv2.imread('krishna_prasad.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```



## ii) Display the video

```py
import cv2
videoCaptureObject = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = videoCaptureObject.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## iii) Display the video by resizing the window
```py
videoCaptureObject = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = videoCaptureObject.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

videoCaptureObject.release()
```



## iv) Rotate and display the video
```py
videoCaptureObject = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = videoCaptureObject.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
videoCaptureObject.release()
cv2.destroyAllWindows()
```








## Output

### i) Write the frame as JPG image
<img width="575" height="462" alt="Screenshot 2025-09-17 210841" src="https://github.com/user-attachments/assets/c29bbb49-7ae5-48ef-a672-e3fd4e229707" />



### ii) Display the video
<img width="563" height="442" alt="Screenshot 2025-09-17 210920" src="https://github.com/user-attachments/assets/f0dd246e-356c-4244-82f0-3d453a33911a" />


### iii) Display the video by resizing the window
<img width="284" height="434" alt="Screenshot 2025-09-17 210948" src="https://github.com/user-attachments/assets/8aaa7b72-47a0-4c5d-8150-21edf49f691a" />




### iv) Rotate and display the video
<img width="333" height="436" alt="Screenshot 2025-09-17 211007" src="https://github.com/user-attachments/assets/27a44172-c25d-4b22-9f82-529c58e0d215" />






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
