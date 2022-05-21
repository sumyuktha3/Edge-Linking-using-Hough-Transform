# Edge-Linking-using-Hough-Transform

## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step1:
Read image and convert it to grayscale image

### Step2:
Find the edges in the image using canny detector and display

### Step3:
Detect points that form a line using HoughLinesP

### Step4:
Draw lines on the image

### Step5:
Display the result

## Program:

### Developed By: S.Sumyuktha Rani
### Register No: 212220230050

```
# Read image and convert it to grayscale image
import cv2 
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("image_line.webp",0)
img_c=cv2.imread("image_line.webp",1)
img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Gray Image')
plt.imshow(img)
plt.show()
# Find the edges in the image using canny detector and display
canny=cv2.Canny(img,120,150)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Canny')
plt.imshow(canny)
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(canny,1,np.pi/180,50,20,2)

# Draw lines on the image
blank_image = np.ones(img.shape, dtype=np.uint8)
for lin in lines:
    x1,y1,x2,y2=lin[0]
    cv2.line(blank_image,(x1,y1),(x2,y2),(255,255,0),2)
    
# Display the result
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Hough Transform')
plt.imshow(blank_image)
plt.show()

```

## Output

### Input image and grayscale image

![s1](https://user-images.githubusercontent.com/75235818/169633279-587b8ba2-59d5-400e-82be-39191d7090b0.jpg)

### Canny Edge detector output

![s2](https://user-images.githubusercontent.com/75235818/169633371-adee6e71-af81-477e-8a4c-6a13425dd734.jpg)

### Display the result of Hough transform

![s3](https://user-images.githubusercontent.com/75235818/169633381-ee24c260-c1b1-4e98-b7d0-afedd9d9800d.jpg)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
