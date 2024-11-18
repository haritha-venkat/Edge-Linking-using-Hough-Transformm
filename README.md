# Edge-Linking-using-Hough-Transformm
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

## PROGRAM:
### Input image
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('color.jpg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
### OUTPUT:
![Screenshot 2024-10-26 112855](https://github.com/user-attachments/assets/e054dc2e-f2c9-4240-b730-a8703fd1d27b)

### grayscale image
```py
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
### OUTPUT:
![Screenshot 2024-10-26 112908](https://github.com/user-attachments/assets/69301546-1ee0-4751-8377-9ba3bf8d58a8)

### Canny Edge detector output
```py
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
### OUTPUT:
![Screenshot 2024-10-26 112931](https://github.com/user-attachments/assets/7fe9afe6-9548-4f70-b38f-b438c8312cbb)

### Display the result of Hough transform
```py
lines = cv2.HoughLinesP(canny_edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=100, maxLineGap=100)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
### OUTPUT:
![Screenshot 2024-10-26 112940](https://github.com/user-attachments/assets/a2c4238a-e103-43d9-a891-e60ee2e02c0c)

## RESULT
Thus,The Python program to detect the lines using Hough Transform run successfully.
