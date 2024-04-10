# EX-08 THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```
DEVELOPED BY: SIVABALAN S
REGISTER NO: 212222240100
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("brba.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("brba.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output
### Original Image
![brba](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/325606a8-bfe8-4c38-89fc-da967e1bef27)

### Global Thresholding
![Screenshot 2024-04-10 110713](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/8cbe88a0-da31-4e82-83e6-6f110efca37b)
![Screenshot 2024-04-10 110852](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/a691b417-d9d4-4b09-be2b-6fadf54d4a3d)

### Adaptive Thresholding
![Screenshot 2024-04-10 110941](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/89ac52bc-829c-4a5d-be30-ffd3bcaa3c3f)
![Screenshot 2024-04-10 110947](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/5bfb948a-97c5-4c2d-8385-a933c8eec9de)
![Screenshot 2024-04-10 110859](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/740b8214-9b9d-4c89-81af-727b4023fa30)
![Screenshot 2024-04-10 110909](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/e8cf2dce-83a3-4c46-aed3-36ab130ef002)
![Screenshot 2024-04-10 110916](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/4ec8cb10-058b-4004-bf51-e02f81b17e61)
![Screenshot 2024-04-10 110924](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/82bcb8bf-4488-4c81-a10c-ced896da2664)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-10 110931](https://github.com/sivabalan28/THRESHOLDING-/assets/113497347/0f8bf7d5-bdf0-4854-aab1-dd8b0c8bcb8a)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
