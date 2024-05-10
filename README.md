# EX-07 Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program
```
NAME: BALAMURUGAN B
REG: 212222230016

import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("bala.png",0)
img_c=cv2.imread("bala.png",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()

canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
lines=cv2.HoughLinesP(canny,1,np.pi/180,
                threshold=80,minLineLength=50,maxLineGap=250)

for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)

plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
![7o](https://github.com/BALA291/Edge-Linking-using-Hough-Transformm/assets/120717501/ac583d4f-0efe-4e64-b42b-0c4be6181de9)


### Canny Edge detector output
![7oi](https://github.com/BALA291/Edge-Linking-using-Hough-Transformm/assets/120717501/700ffb86-71b7-44f8-b94e-28bdecb02d76)


### Display the result of Hough transform
![7oii](https://github.com/BALA291/Edge-Linking-using-Hough-Transformm/assets/120717501/9739a0b9-07af-4b86-b962-a24dce41109c)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
