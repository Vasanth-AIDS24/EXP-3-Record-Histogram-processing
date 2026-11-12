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
**Name:** SHAABIN R S
**Register No:** 212224230259

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
<img width="487" height="552" alt="image" src="https://github.com/user-attachments/assets/c9ff97ca-63f8-41db-8a76-21b15d1aafe0" />


<img width="770" height="563" alt="image" src="https://github.com/user-attachments/assets/a087df4d-b9f7-4849-adbe-316482772373" />



### Equalised Histogram:

<img width="722" height="555" alt="image" src="https://github.com/user-attachments/assets/ce226975-fcab-4de9-8716-856e5f478363" />


<img width="502" height="541" alt="image" src="https://github.com/user-attachments/assets/06177f50-8192-4b85-9dae-a5b152d9b84b" />


### Histogram of Grayscale Image and any channel of Color Image:
<img width="512" height="552" alt="image" src="https://github.com/user-attachments/assets/686aab77-cfc7-43aa-90ef-f100edcb589a" />

<img width="771" height="552" alt="image" src="https://github.com/user-attachments/assets/1a7b741f-463d-41cf-859f-7020abb39342" />

### Histogram Equalization of Grayscale Image:
<img width="436" height="480" alt="image" src="https://github.com/user-attachments/assets/d0a953fa-c75e-440a-a3b0-3dde8a7d794a" />

<img width="427" height="471" alt="image" src="https://github.com/user-attachments/assets/82d0ce16-623e-4189-ad9e-be394c4e0a5c" />

<img width="691" height="421" alt="image" src="https://github.com/user-attachments/assets/17125739-993d-4911-b0a7-b61d12fcf2dd" />

<img width="697" height="435" alt="image" src="https://github.com/user-attachments/assets/f50f6b8f-46d4-4cab-98f8-94b0481189c8" />

## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
