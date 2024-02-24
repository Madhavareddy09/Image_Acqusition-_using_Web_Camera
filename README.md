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
<br>
Use cv2.VideoCapture(0) to access web camera

### Step 2:
<br>
Use cv2.imread to read the video or image
### Step 3:
<br>
Use cv2.imwrite to save the image
### Step 4:
<br>
Use cv2.imshow to show the video

### Step 5:
<br>
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
### Developed By : K MADHAVA REDDY
### Register No : 212223240064
```
## i) Write the frame as JPG file
```python
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    cap,frame=videoCaptureObject.read()
    cv2.imwrite("MadhavaReddy.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('video capture',frame)
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
    cv2.imshow('Video Capture',image)
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
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## Output

### i) Write the frame as JPG image
![Screenshot 2024-02-24 235240](https://github.com/Madhavareddy09/Image_Acqusition-_using_Web_Camera/assets/145742470/c5e4b9cd-4d5d-4315-90f2-c4a99dc8d04d)


### ii) Display the video
![Screenshot 2024-02-24 235834](https://github.com/Madhavareddy09/Image_Acqusition-_using_Web_Camera/assets/145742470/6553a1f6-1609-4136-8eb3-ca21e42af464)


### iii) Display the video by resizing the window

![Screenshot 2024-02-25 000710](https://github.com/Madhavareddy09/Image_Acqusition-_using_Web_Camera/assets/145742470/fff800db-701c-4b97-b74c-e79fedde707d)

### iv) Rotate and display the video
![Screenshot 2024-02-25 000853](https://github.com/Madhavareddy09/Image_Acqusition-_using_Web_Camera/assets/145742470/8baac1da-8427-470f-ae74-70dae5e93902)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
