# EDGE-DETECTION
# Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

# Software Required:
Anaconda - Python 3.7

# Algorithm:
## Step1:
Import all the necessary modules for the program.

## Step2:
Load a image using imread() from cv2 module.

## Step3:
Convert the image to grayscale

## Step4:
Using Sobel operator from cv2,detect the edges of the image.

## Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

# Program:
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('butterfly.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# 1) Apply Sobel operator

sobelx  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 1, dy = 0, ksize = 3) 
sobely  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 0, dy = 1, ksize = 3)

sobelx = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)  # Sobel X
sobely = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3)  # Sobel Y
sobel_combined = cv2.magnitude(sobelx, sobely) 

plt.figure(figsize = (12, 16))
plt.subplot(321); plt.axis('on'); plt.imshow(image[:,:,::-1]); plt.title('Original')
plt.subplot(322); plt.axis('on'); plt.imshow(gray_image, cmap='gray');plt.title('Grayscale') 
plt.subplot(323); plt.axis('on'); plt.imshow(sobelx);plt.title('Sobel-X Edge Map')
plt.subplot(324); plt.axis('on'); plt.imshow(sobely);plt.title('Sobel-Y Edge Map')

plt.figure(figsize = (12, 6))
plt.axis('off'); plt.imshow(sobel_combined, cmap='gray' ); plt.title('sobel_combined ');


# 2) Apply Laplacian operator

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.figure(figsize = (12, 16))
plt.subplot(121); plt.axis('off'); plt.imshow(gray_image, cmap='gray'); plt.title('Input Image (Gray Image)')
plt.subplot(122);plt.imshow(laplacian, cmap='gray');plt.axis('off'); plt.title('Output Image (laplacian)')


## 3) Canny Edge Detector

edges = cv2.Canny(gray_image, threshold1 = 180, threshold2 = 200)

plt.figure(figsize = (12, 16))
plt.subplot(121); plt.axis('off'); plt.imshow(gray_image, cmap='gray'); plt.title('Input image (Gray Image)')
plt.subplot(122);plt.imshow(edges, cmap='gray');plt.axis('off'); plt.title('Canny Edge Map')

```
# Output:
## SOBEL EDGE DETECTOR
<img width="1303" height="462" alt="image" src="https://github.com/user-attachments/assets/d64c8bc6-5249-4d20-a4a6-ee846da925a3" />
<img width="1178" height="635" alt="image" src="https://github.com/user-attachments/assets/a129fad8-1b3f-485a-8fe6-22c64a78132e" />
<img width="1368" height="486" alt="image" src="https://github.com/user-attachments/assets/7cbff6c5-eae4-4213-ac2a-69fcc4b0e07f" />


## LAPLACIAN EDGE DETECTOR
<img width="1200" height="414" alt="image" src="https://github.com/user-attachments/assets/ec71af87-6d29-4065-ae55-32ebc3766f0a" />


## CANNY EDGE DETECTOR
<img width="1234" height="425" alt="image" src="https://github.com/user-attachments/assets/1de2f269-354f-4e3f-8a1d-507bb77a4921" />


# Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
