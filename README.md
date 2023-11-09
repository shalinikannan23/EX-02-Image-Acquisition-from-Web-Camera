# EX-2 Image Acquisition from Web Camera
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE:** 23.08.2023
### Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
### Software Used
- Anaconda - Python 3.7
### Algorithm
- Step 1: Import the cv2 and numpy package.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Developed By: ROHIT JAIN D
- Step 2: Read the Video frame using the cv2.VideoCapture(0)&emsp;&emsp;&emsp;&emsp;&emsp;Register Number: 212222230120
- Step 3: Write the image using imwrite().
- Step 4: Display the frame using the imshow().
- Step 5: Divide the frame into halves and assign the smaller frame
- Step 6: Rotate the frame using the cv2.rotate().
### Program:
<table>
    <tr>
        <td>
            
#### i) Write the frame as JPG file
```Python
import cv2
Obj=cv2.VideoCapture(0)
while (True):
    ret,fr=Obj.read()
    cv2.imwrite("NewPicture.jpg",fr)
    result=True
Obj.release()
cv2.destroyAllWindows()
```
</td>
<td>
    
#### Output:
![Screenshot 2023-09-10 123250](https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/4f865b2c-e44c-4f64-b03c-92ea28706ef9)

</td>
</tr>
</table>
<table>
<tr>
        <td>
            
#### ii) Display the video
```Python
import cv2
img=cv2.VideoCapture(0)
while(True):
    image,fr=img.read()
    cv2.imshow('ROHIT JAIN D 212222230120',fr)
    cv2.imwrite("NewPicture.jpg",fr)
    if cv2.waitKey(1) =ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```

</td>
<td>
    
#### Output:<br>
  <img src="https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/041ca5a0-47f6-40f3-946f-453cf9c6f4e8">
</td>
</tr>

<tr>
    <td>

    
#### iii) Display the video by resizing the window
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,fr=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(fr.shape,np.uint8)
    sfram=cv2.resize(fr,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=sfram
    image[height//2:,:width//2]=sfram
    image[:height//2,width//2:]=sfram
    image[height//2:,width//2:]=sfram
    cv2.imshow('ROHITJAIN D 212222230120',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
</td>
     <td>

#### Output:<br>
  <img src="https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/2add4767-9684-44ea-9c3d-cc82d6eeb767">

</td>   
</tr>
<tr>
    <td>
        
#### iv) Rotate and display the video
```Python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,fr=cap.read() 
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(fr.shape, np.uint8) 
    sfram=cv2.resize(fr,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=cv2.rotate(sfram,cv2.ROTATE_180)
    image[height//2:,:width//2]=sfram 
    image[:height//2,width//2:]=sfram
    image[height//2:,width//2:]=cv2.rotate(sfram,cv2.ROTATE_180)
    cv2.imshow('ROHIT JAIN D 212222230120',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
</td>
<td>
    
### Output:<br>
  <img src="https://github.com/ROHITJAIND/Image-Acquisition-from-Web-Camera/assets/118707073/22431046-583e-4723-8ce9-cfb8c53b6541">
  </td>
  </tr>
</table>

### Result:
Thus the image is accessed from webcamera and displayed using openCV.
