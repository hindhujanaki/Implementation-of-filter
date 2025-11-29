# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.
### Step2
Convert the image from BGR to RGB
### Step3
Apply the required filters for the image separately.
### Step4
Plot the original and filtered image by using matplotlib.pyplot.
### Step5
End the program.

## Program:
### Developed By   :HINDHU.G
### Register Number:212223230079
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1 = cv2.imread("panda.jpeg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

```
ii) Using Weighted Averaging Filter
```Python
kernel = np.ones((11, 11), np.float32) / 121
averaging_image = cv2.filter2D(image2, -1, kernel)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(averaging_image)
plt.title("Averaging Filter Image")
plt.axis("off")
plt.show()

```
iii) Using Gaussian Filter
```Python
kernel1 = np.array([[1, 2, 1],
                    [2, 4, 2],
                    [1, 2, 1]]) / 16

weighted_average_image = cv2.filter2D(image2, -1, kernel1)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(weighted_average_image)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

```
iv)Using Median Filter
```Python
gaussian_blur = cv2.GaussianBlur(image2, (11, 11), 0)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
sharpened_image = cv2.filter2D(gaussian_blur, -1, kernel1)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(sharpened_image)
plt.title("Sharpened Image (Laplacian Kernel)")
plt.axis("off")
plt.show()

```
ii) Using Laplacian Operator
```Python
laplacian = cv2.Laplacian(image2, cv2.CV_64F)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Operator Image")
plt.axis("off")
plt.show()

```

## OUTPUT:
### 1. Smoothing Filters
i) Using Averaging Filter

![image](https://github.com/user-attachments/assets/b773894f-ad67-4516-b84e-3aa52b6a8fef)

ii)Using Weighted Averaging Filter

![image](https://github.com/user-attachments/assets/76924ed7-19eb-4c71-8dff-42a10c590d38)

iii)Using Gaussian Filter

![image](https://github.com/user-attachments/assets/b41f3191-89c3-48fb-8abe-b1b05760252c)

iv) Using Median Filter

![image](https://github.com/user-attachments/assets/975b6804-c9c3-4644-a852-29cbf67b41f4)


### 2. Sharpening Filters

i) Using Laplacian Kernal

![image](https://github.com/user-attachments/assets/804816bc-ea3c-4fc0-812c-4237b707ba73)

ii) Using Laplacian Operator

![image](https://github.com/user-attachments/assets/f41adb43-0931-413e-9a84-bddc9f12ef1e)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
