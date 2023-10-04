<img width="338" alt="image" src="https://github.com/Prakashmathi2004/EDGE--LINKING-HOUGH-TRANSFORM/assets/118350045/536a60e4-bb1b-47e3-9d48-17997dc5df24"># EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.
<br>

### Step2:
Find the edges in the image using canny detector and display.
<br>

### Step3:
Detect points that form a line using HoughLinesP.
<br>

### Step4:
Draw lines on the image.
<br>

### Step5:
Display the result.
<br>


## Program:

DEVELOPED BY : PRAKASH M

REGISTER NUMBER : 212222100035

## Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("d.jpg",0)
img_s=cv2.imread("d.jpg",1)
img_s=cv2.cvtColor(img_s,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_s)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```

## Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```

## Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```

## Draw lines on the image
```
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_s,(x1,y1),(x2,y2),(255,0,0),3)
```

## Display the result
```
plt.imshow(img_s)
plt.title("Result Image")
plt.axis("off")
plt.show()
```

## Output

## Input image and grayscale image

<img width="589" alt="image" src="https://github.com/Prakashmathi2004/EDGE--LINKING-HOUGH-TRANSFORM/assets/118350045/50bc7fb1-88b5-4056-9f52-55f2b7ac9db9">

<br>
<br>

## Canny Edge detector output

<img width="349" alt="image" src="https://github.com/Prakashmathi2004/EDGE--LINKING-HOUGH-TRANSFORM/assets/118350045/ecb8b99b-0584-46a6-b8c8-61287d8cad47">

<br>
<br>


## Display the result of Hough transform

<img width="338" alt="image" src="https://github.com/Prakashmathi2004/EDGE--LINKING-HOUGH-TRANSFORM/assets/118350045/742e4974-4610-4fb9-ae07-02ed0f230038">


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
