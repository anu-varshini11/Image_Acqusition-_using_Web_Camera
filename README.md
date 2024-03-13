# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.


### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image.

### Step 6:
End Program with 'q'. Allow the program to be terminated by pressing the 'q' key.

## Program:
``` Python
### Developed By: Anu Varshini M B
### Register No: 212223240010

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("img.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```python

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```python

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
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```python

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![DIP2](https://github.com/anu-varshini11/Image_Acqusition-_using_Web_Camera/assets/138969827/750880ee-a60e-4c83-b4a8-cc7f5791339a)



### ii) Display the video

![dip3](https://github.com/anu-varshini11/Image_Acqusition-_using_Web_Camera/assets/138969827/bedc06e7-4792-4994-941b-7f212157a866)



### iii) Display the video by resizing the window

![dip5](https://github.com/anu-varshini11/Image_Acqusition-_using_Web_Camera/assets/138969827/bb321d86-2104-41f3-884f-f60533eeba9e)



### iv) Rotate and display the video

![dip6](https://github.com/anu-varshini11/Image_Acqusition-_using_Web_Camera/assets/138969827/c1ac0626-6d5c-42a5-8fb2-d37c875a4472)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
