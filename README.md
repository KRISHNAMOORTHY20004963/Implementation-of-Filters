# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules


### Step2
For performing smoothing operation on a image.

Average filter:
```python

avg_kernel=np.ones((13,13),np.float32)/169
average_filter_image=cv2.filter2D(image,-1,avg_kernel)
```
Weighted average filter :
```python
wt_avg_kernel=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
wt_average_filter_image=cv2.filter2D(image,-1,wt_avg_kernel)
```
Gaussian Blur:
```python
gaussian_blur=cv2.GaussianBlur(image,(31,31),0,0)
```
Median filter:
```python
median_blur=cv2.medianBlur(image,11)
```


### Step3
For performing sharpening on a image.

Laplacian Kernel:
```python
lap_kernel=np.array([[-1,-1,-1],[-1,8,-1],[-1,-1,-1]])
lap_image=cv2.filter2D(image,-1,lap_kernel)
```
Laplacian Operator:
```python
Lap_sharp=cv2.Laplacian(image,cv2.CV_64F)
```




### Step4
Display all the images with their respective filters. 

## Program:
### Developed By   : KRISHNA MOORTHY S
### Register Number: 212220230025
</br>

```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread('black panther.jpg')
img1=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

```

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel=np.ones((13,13),np.float32)/169
image=cv2.filter2D(img1,-1,kernel)
plt.figure(figsize=(10,10))

plt.subplot(1,2,1)

plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image)


```
ii) Using Weighted Averaging Filter
```Python

kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image1=cv2.filter2D(img1,-1,kernel2)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image1)


```
iii) Using Gaussian Filter
```Python

img4=cv2.GaussianBlur(src=img1,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)

plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)


```

iv) Using Median Filter
```Python
img5=cv2.medianBlur(src=img1,ksize=11)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)


```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
img6=cv2.filter2D(img1,-1,kernel3)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img6)



```
ii) Using Laplacian Operator
```Python

img7=cv2.Laplacian(img1,cv2.CV_64F)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img7)



```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter



![ex 6 (1)](https://user-images.githubusercontent.com/75241177/167810336-1af192c8-8ad1-44b7-bd52-c9108cc063c4.png)

ii) Using Weighted Averaging Filter


![ex 6(2)](https://user-images.githubusercontent.com/75241177/167810484-18f171df-6716-4330-8231-5e2ccf925a14.png)

iii) Using Gaussia!
n Filter


![ex 6(3)](https://user-images.githubusercontent.com/75241177/167810542-3e20ad1a-848e-4ffb-93cf-9405942605fa.png)

iv) Using Median Filter
!
![ex 6(4)](https://user-images.githubusercontent.com/75241177/167810560-bf61fd3c-7199-4969-b432-e2a055b5dc04.png)

### 2. Sharpening Filters


i) Using Laplacian Kernal


![ex 6 (5)](https://user-images.githubusercontent.com/75241177/167810624-e48de9f1-e1fa-4b3e-b74b-62545a74af13.png)


ii) Using Laplacian Operator
![![ex 6 (6)](https://user-images.githubusercontent.com/75241177/167810660-7ebe2926-fd8a-4a63-89a2-4c78e573e753.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
