# EX-2 Image Acquisition from Web Cameraa
### Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
- i) Write the frame as JPG.
- ii) Display the video.
- iii) Display the video by resizing the window.
- iv) Rotate and display the video.
### Software Used
- Anaconda - Python 3.7
### Algorithm
- Step 1: Import the cv2 and numpy package.
- Step 2: Read the Video frame using the cv2.VideoCapture(0)
- Step 3: Write the image using imwrite().
- Step 4: Display the frame using the imshow().
- Step 5: Divide the frame into halves and assign the smaller frame
- Step 6: Rotate the frame using the cv2.rotate().
### Program:
```
Developed By: ROHIT JAIN D
Register No: 212222230120
```
#### i) Write the frame as JPG file
```Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result = True
videoCaptureObject.release()
cv2.destroyAllWindows()
```
- Output:
![Screenshot 2023-09-10 123250](https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/4f865b2c-e44c-4f64-b03c-92ea28706ef9)

#### ii) Display the video
```Python
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('ROHIT JAIN D 212222230120',frame)
    cv2.imwrite("NewPicture.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```
- Output:<br>
  <img height=20% width= 50% src="https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/041ca5a0-47f6-40f3-946f-453cf9c6f4e8">



#### iii) Display the video by resizing the window

```Python
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
    cv2.imshow('ROHITJAIN D 212222230120',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
- Output:<br>
  <img height=20% width= 50% src="https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/2add4767-9684-44ea-9c3d-cc82d6eeb767">

#### iv) Rotate and display the video

```Python
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
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('ROHIT JAIN D 212222230120', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
- Output:<br>
  <img height=20% width= 50% src="https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/22431046-583e-4723-8ce9-cfb8c53b6541">


### Result:
Thus the image is accessed from webcamera and displayed using openCV.
