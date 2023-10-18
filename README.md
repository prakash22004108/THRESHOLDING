# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import the necessary packages.
<br>

### Step2:
Create the text using cv2.putText.
<br>

### Step3:
Create the structuring element.
<br>

### Step4:
Erode the image using cv2.erode().
<br>

### Step5:
Dilate the imge using cv2.dilate().
<br>

## Program:
```
DEVELOPED BY :PRAKASH R
REG NO: 212222240074
```


# Load the necessary packages:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```




# Read the Image and convert to grayscale:
```
image=cv2.imread("gt.jpeg")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
grayscale_image=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(grayscale_image,'gray')
plt.title('Gray image')
plt.axis('off')
```








# Use Global thresholding to segment the image:
```
ret,thresh_img1=cv2.threshold(grayscale_image,81,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(grayscale_image,81,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(grayscale_image,81,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(grayscale_image,80,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(grayscale_image,105,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image:
```
thresh_img7=cv2.adaptiveThreshold(grayscale_image,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(grayscale_image,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Use Otsu's method to segment the image :
```
ret,thresh_img6=cv2.threshold(grayscale_image,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Display the results:
```
titles=["Gray Image", "Threshold Image (Binary)", "Threshold Image (Binary Inverse)", "Threshold Image (To Zero)"
       , "Threshold Image (To Zero-Inverse)", "Threshold Image (Truncate)", "Otsu", "Adaptive Threshold (Mean)", "Adaptive Threshold (Gaussian)"]
images=[grayscale_image, thresh_img1, thresh_img2, thresh_img3, thresh_img4, thresh_img5, thresh_img6, thresh_img7, thresh_img8]

for i in range(0,9):
    plt.figure(figsize=(5,5))
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






## Output:

### Original Image:
![Screenshot 2023-10-04 084148](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/6968359f-29f3-4d92-ad25-5211f0159b3c)
<br>
<br>
<br>
<br>
<br>

### Global Thresholding:
![Screenshot 2023-10-04 084158](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/18d22c1b-10cb-4294-a94d-13fce6a636ba)

![Screenshot 2023-10-04 084208](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/fd7c1036-bcbf-4277-a77e-3af55c628118)

![Screenshot 2023-10-04 084215](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/76b1ef45-5315-486a-877a-79d980b0ef24)

![Screenshot 2023-10-04 084224](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/1a80d5dd-7406-4931-81a6-bbb173b60afa)

![Screenshot 2023-10-04 084230](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/03681bb0-fa1a-4458-859f-bcc8c7de7d3d)
<br>
<br>
<br>
<br>
<br>

### Adaptive Thresholding:
![Screenshot 2023-10-04 084246](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/86e629b0-10db-4ea8-b4e2-22b775d0c523)

![Screenshot 2023-10-04 085528](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/13b4a19b-9fec-4acc-bb9f-76e9b5d54092)

<br>
<br>
<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method:
![Screenshot 2023-10-04 084238](https://github.com/JeevaGowtham-S/THRESHOLDING/assets/118042624/01d76ac8-7f41-42e7-9311-dad4e1374c8e)
<br>
<br>
<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
