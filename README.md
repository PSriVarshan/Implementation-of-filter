# Implementation-of-filter
## Aim:
### To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
### Anaconda - Python 3.7

## Algorithm:
### Step1

#### Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step2

#### Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step3

#### Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.

### Step4

#### Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.


### Step5

#### Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.



### Step6:

#### Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.


## Program:
### Developed By   :  Sri Varshan P
### Register Number: 212222240104
</br>

### 1. Smoothing Filters

#### Import necessary Libraries
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
#### (i) Using Averaging Filter
```Python

image1 = cv2.imread('chad.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')

```
#### (ii) Using Weighted Averaging Filter
```Python

image1 = cv2.imread('chad.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)


kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')

```
#### (iii) Using Gaussian Filter
```Python


image1 = cv2.imread('chad.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')




```

#### (iv) Using Median Filter
```Python


image1 = cv2.imread('chad.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')



```

### 2. Sharpening Filters
#### (i) Using Laplacian Kernal
```Python

image1 = cv2.imread('chad.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')

```
#### (ii) Using Laplacian Operator
```Python
image1 = cv2.imread('chad.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')

```

## OUTPUT:
### 1. Smoothing Filters
</br>

#### (i) Using Averaging Filter
</br>
</br>

![image](https://github.com/PSriVarshan/Implementation-of-filter/assets/114944059/a0532fac-7da5-4b67-812e-bc8d718da502)

</br>
</br>

#### (ii) Using Weighted Averaging Filter
</br>
</br
  
![image](https://github.com/PSriVarshan/Implementation-of-filter/assets/114944059/e8fc6b09-1e0c-4345-b17a-ef1a98710ef3)

</br>
</br>

#### (iii) Using Gaussian Filter
</br>
</br>

![image](https://github.com/PSriVarshan/Implementation-of-filter/assets/114944059/1a06f411-20b1-4cf5-a92e-f47871d0eefc)

</br>
</br>

#### (iv) Using Median Filter
</br>
</br>

![image](https://github.com/PSriVarshan/Implementation-of-filter/assets/114944059/f866756d-9969-48ac-82f6-6b51b00019ad)

</br>
</br>

### 2. Sharpening Filters
</br>

#### (i) Using Laplacian Kernal
</br>
</br>

![image](https://github.com/PSriVarshan/Implementation-of-filter/assets/114944059/d33e59b0-471c-4f25-ba0e-e0c6b4e2c6ed)

</br>
</br>

#### (ii) Using Laplacian Operator
</br>
</br>

![image](https://github.com/PSriVarshan/Implementation-of-filter/assets/114944059/b3eef065-0ed3-429b-8ed4-03fd5e23d886)

</br>
</br>

## Result:
### Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
