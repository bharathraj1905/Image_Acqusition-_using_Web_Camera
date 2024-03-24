# Image_Acqusition-_using_Web_Camera
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
Import cv2 and capture the viedo using cv2.ViedoCapture(0).

### Step 2:
Write the capture image using cv2.imwrite("NewPicture.jpg",frame).

### Step 3:
Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).

### Step 4:
Display the image until the loop gets over.

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).

## Program:

### Developed By : Barathraj.B
### Register No : 212222230019

## i) Write the frame as JPG file
```python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("bharathraj.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Fox',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230019_bharathraj',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230019_bharathraj',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image

![image](https://github.com/bharathraj1905/Image_Acqusition-_using_Web_Camera/assets/121490575/df71db39-50e7-49d0-bf06-b2c7034a028d)


### ii) Display the video

![image](https://github.com/bharathraj1905/Image_Acqusition-_using_Web_Camera/assets/121490575/8b548b97-e447-4cf8-9a4f-e819b2326400)


### iii) Display the video by resizing the window

![image](https://github.com/bharathraj1905/Image_Acqusition-_using_Web_Camera/assets/121490575/de16379c-dbfd-4325-a5af-71616c37e6e1)


### iv) Rotate and display the video

![image](https://github.com/bharathraj1905/Image_Acqusition-_using_Web_Camera/assets/121490575/66b4665e-9b44-4f04-b785-75c457e472dd)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
