## EX NO:02
## DATE:7.4.22
# <p align="center">Image-Acquisition-from-Web-Camera
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 

ii) Display the video

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:
display the image until the loop gets over

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:
``` Python
### Developed By: Prasanna Kumar M
### Register No: 212220230035
## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
cv2.imwrite("NewPicture.jpg",frame)
## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    cv2.imshow("NewPicture",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    cv2.imshow("NewPicture.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    cv2.imshow("NewPicture.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![image](https://user-images.githubusercontent.com/75235128/161367607-f29bdf7e-ea2f-441c-9c10-e3653f01e3df.png)

### ii) Display the video
![image](https://user-images.githubusercontent.com/75235090/161997842-45118499-5263-454a-9f78-03802bd32bf3.png)

### iii) Display the video by resizing the window
![image](https://user-images.githubusercontent.com/75235090/161996922-5964286b-e9c0-4cb1-9f52-44034289fb6b.png)


### iv) Rotate and display the video
![image](https://user-images.githubusercontent.com/75235090/161999196-91ee6100-00cb-4eee-b28c-8ca255f6c954.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
