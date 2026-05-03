# image-enhancement-filters-opencv

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
- Step 1
  Import the necessary libraries (cv2, numpy, matplotlib.pyplot) and read the input image using cv2.imread().

- Step 2
  Define the kernels for the filters, such as an averaging kernel for smoothing (e.g., a 5x5 matrix of ones divided by 25) and a Laplacian kernel for sharpening.

- Step 3
  Apply the smoothing filters to the original image using functions like cv2.filter2D() for the averaging filter, cv2.GaussianBlur() for Gaussian blur, and cv2.medianBlur() for median blur.

- Step 4
  Apply the sharpening filter using cv2.filter2D() with the Laplacian kernel, and then add this filtered output to the original image to create the final sharpened image.


- Step 5
  
Display the original, smoothed, and sharpened images side-by-side using matplotlib.pyplot.imshow() and plt.subplot() for comparison.

 

## Program
## Developed By : HARINI S
## Register Number: 212224240049

# 1. Smoothing Filters

## i) Using Averaging Filter

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread(r"C:\Users\admin\Downloads\baseball.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```



## ii) Using Weighted Averaging Filter

```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## iv)Using Median Filter

```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

# 2. Sharpening Filters
## i) Using Laplacian Linear Kernal

```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

## ii) Using Laplacian Operator
```
laplacian = cv2.Laplacian(image2, cv2.CV_64F)
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1, 2, 2)
laplacian_abs = np.uint8(np.absolute(laplacian))
plt.imshow(laplacian_abs, cmap='gray')
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output
## i) Using Averaging Filter
<img width="731" height="238" alt="image" src="https://github.com/user-attachments/assets/27b9bbd2-2178-46da-9c02-91f75be5cb55" /><br>
## ii) Using Weighted Averaging Filter
<img width="564" height="201" alt="image" src="https://github.com/user-attachments/assets/329730e1-2ac2-4e60-b2ed-0c56a10a267a" /><br>

## iii) Using Gaussian Filter
<img width="547" height="183" alt="image" src="https://github.com/user-attachments/assets/26519235-c19e-4dc0-8565-a8af99c7cb2a" /><br>

## iv)Using Median Filter
<img width="819" height="243" alt="image" src="https://github.com/user-attachments/assets/b831f7fc-34d0-44fa-9978-23d667706cba" /><br>


# 2. Sharpening Filters
## i) Using Laplacian Linear Kernal
<img width="585" height="185" alt="image" src="https://github.com/user-attachments/assets/7d10236a-1bec-4055-8e6f-360994938aec" /><br>

## ii) Using Laplacian Operator
<img width="573" height="181" alt="image" src="https://github.com/user-attachments/assets/cf3d2f25-2305-48a1-b2b2-74ddf7a38a5c" /><br>

## Result:
Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.






