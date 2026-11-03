# Histogram Equalization Using OpenCV (Grayscale & Color Images)
## Aim
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image
Plot histogram of the grayscale image
Apply histogram equalization on grayscale image
Read and display a color image
Plot histogram of B, G, R channels
Convert image to HSV color space
Apply histogram equalization on the Value (V) channel
Convert the enhanced image back to BGR format
Display original and enhanced images with histograms
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm
### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image parrot.jpg in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

## Program
### Developed By:
### Name: KIRUTIKA K R
### Register No: 212224230128
1.Import the required libraries and read the grayscale image.

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('Eiffel Tower.png',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
2.Plot the histogram of the grayscale image.
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
3.Apply histogram equalization.
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```
4.Display the equalized grayscale image.
```
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
5.Display the original and equalized color images.
```
img = cv2.imread('Eiffel Towe.png', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
```
6.Display the original and equalized images along with their histograms.
```
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output
<img width="461" height="543" alt="image" src="https://github.com/user-attachments/assets/268611ae-ad89-49c3-a5f9-3be392cc2213" />

<img width="522" height="381" alt="image" src="https://github.com/user-attachments/assets/57bb0112-5674-4c5e-9a76-94566be0e305" />

<img width="511" height="387" alt="image" src="https://github.com/user-attachments/assets/0f42969b-7a1e-4266-9af2-ed337779b13c" />

<img width="512" height="547" alt="image" src="https://github.com/user-attachments/assets/c4fc654b-107c-4d38-92b2-b0f186ae1d3e" />

<img width="708" height="427" alt="image" src="https://github.com/user-attachments/assets/6b5674cb-8ec1-4e67-a6fb-6e4fccad6b48" />

<img width="855" height="677" alt="image" src="https://github.com/user-attachments/assets/096efc92-5173-4d42-a02f-60e430af8c4a" />


## Result
Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
