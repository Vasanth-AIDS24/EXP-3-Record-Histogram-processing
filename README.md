# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim:

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used:

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm:

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

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

---


## Developed By:
**Name:** Vasanth P
**Register No:** 212224230295

## Program:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg",cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```
```python
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
```python
img = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg", cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
```
```python
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
##  Output:

### ORIGINAL IMAGE:

<img width="452" height="530" alt="image" src="https://github.com/user-attachments/assets/fca0fb73-3197-4a4b-870c-11d38527e5c3" />

<img width="810" height="537" alt="image" src="https://github.com/user-attachments/assets/79164b05-17ef-4453-a9cd-572508357eb6" />



### Equalised Histogram:

<img width="780" height="535" alt="image" src="https://github.com/user-attachments/assets/a0f673bf-74fa-4233-9452-8b69a09053bd" />


<img width="590" height="525" alt="image" src="https://github.com/user-attachments/assets/bd620cda-6d1e-4830-ab00-1b203f62a6a5" />


### Histogram of Grayscale Image and any channel of Color Image:

<img width="532" height="522" alt="image" src="https://github.com/user-attachments/assets/712abb4d-6ecd-47db-a42c-7721f4e234e8" />

<img width="847" height="517" alt="image" src="https://github.com/user-attachments/assets/ce2eaa7c-20c3-42c6-b64e-f3991f0f7b59" />


### Histogram Equalization of Grayscale Image:

<img width="928" height="325" alt="image" src="https://github.com/user-attachments/assets/a3dd2930-cf42-463c-98fe-98ae3fb97fa6" />


<img width="962" height="265" alt="image" src="https://github.com/user-attachments/assets/af0a4412-8eab-4fa9-9992-f8a03fdd91ad" />


## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
