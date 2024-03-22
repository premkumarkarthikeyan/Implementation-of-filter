# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.
### Step2
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.
### Step3
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step4
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.
### Step5
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.
## Program:

Developed By : PREMKUMAR K

Register Number : 212222230111


### 1. Smoothing Filters

i) Using Averaging Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('pred.jpg')
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
ii) Using Weighted Averaging Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('pred.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')

```
iii) Using Gaussian Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('pred.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

iv) Using Median Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('pred.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('pred.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
ii) Using Laplacian Operator
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('pred.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:

### 1. Smoothing Filters

i) Using Averaging Filter

![313939753-d2a59b70-bc04-446d-b1b9-2de16ef3e12a](https://github.com/premkumarkarthikeyan/Implementation-of-filter/assets/119476243/ba769e3e-401c-4eea-ae7c-d3b7f9df78db)



ii) Using Weighted Averaging Filter

![313939825-afef0ece-dd5b-4f09-a00d-80ed046f0b7d](https://github.com/premkumarkarthikeyan/Implementation-of-filter/assets/119476243/3d2f9aad-89e7-4697-bf8f-0ec63828973b)



iii) Using Gaussian Filter

![313939924-4ff7991d-bc88-4ea1-ba1b-65fa2973268e](https://github.com/premkumarkarthikeyan/Implementation-of-filter/assets/119476243/632e3985-bc01-44e9-a363-6ec75ff210ea)




iv) Using Median Filter

![313940217-c3b42dc3-c99a-450a-86a4-d29ae1b2866c](https://github.com/premkumarkarthikeyan/Implementation-of-filter/assets/119476243/4edccdfc-8323-410d-9436-8f38dbaf2e20)


### 2. Sharpening Filters


i) Using Laplacian Kernal

![313940352-8b33f933-af99-40e8-8371-bc38c9874b98](https://github.com/premkumarkarthikeyan/Implementation-of-filter/assets/119476243/9e10b69d-dada-41c3-83cb-1e0dc3614c93)


ii) Using Laplacian Operator

![313940409-d2fe411d-1260-44d0-8477-7e466fbb194b](https://github.com/premkumarkarthikeyan/Implementation-of-filter/assets/119476243/8a061fe2-37fe-4497-837e-fe97dbeedb6f)




## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
