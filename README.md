# EX NO :06 EDGE-DETECTION
# Name : Naveenkumar M
# Ref No: 212224230183
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## program:
~~~python
 import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('naveen.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
 Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('on')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off') 

~~~
## Output:
### SOBEL EDGE DETECTOR

<img width="844" height="549" alt="image" src="https://github.com/user-attachments/assets/4c1fbc3d-2785-44e0-b2d7-abc450b4ff5e" />

### LAPLACIAN EDGE DETECTOR
<img width="881" height="577" alt="image" src="https://github.com/user-attachments/assets/a6adf64a-09e7-4474-95d1-321afcd0e98e" />



### CANNY EDGE DETECTOR
<img width="622" height="520" alt="image" src="https://github.com/user-attachments/assets/a29778f8-62c7-488f-872c-8cb6d8afc473" />


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
