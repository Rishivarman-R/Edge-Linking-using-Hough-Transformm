# Edge-Linking-using-Hough-Transformm
## Name : Rishivaarman R
## Reg no.: 212224100050
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
## Program:
### Input image and grayscale image:
```
import numpy as np
import cv2
import matplotlib.pyplot as plt

gray = cv2.imread('moon.jpg', cv2.IMREAD_GRAYSCALE)
img_color = cv2.imread('moon.jpg', cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)
gray_rgb = cv2.cvtColor(gray, cv2.COLOR_GRAY2RGB)

gray = cv2.GaussianBlur(gray, (3, 3), 0)

plt.figure(figsize=(13, 13))
plt.subplot(1, 2, 1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1, 2, 2)
plt.imshow(gray_rgb, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Canny Edge detector :
```
canny = cv2.Canny(gray, 120, 150)

plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Display the result of Hough transform:
```
lines = cv2.HoughLinesP(canny, 1, np.pi/180, threshold=80, minLineLength=50, maxLineGap=250)

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)

plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="1297" height="369" alt="Screenshot 2025-10-04 110323" src="https://github.com/user-attachments/assets/ef29c832-2b95-4f72-a466-afe57c69b109" />


### Canny Edge detector output
<img width="639" height="405" alt="Screenshot 2025-10-04 110334" src="https://github.com/user-attachments/assets/d1be0369-4fad-40db-a648-2cec3e096b56" />

### Display the result of Hough transform
<img width="671" height="399" alt="Screenshot 2025-10-04 110347" src="https://github.com/user-attachments/assets/ce161fd4-9fd6-467b-9aa3-a9f8d56778ca" />


## Result:
Thus, the image has been successfully converted.
