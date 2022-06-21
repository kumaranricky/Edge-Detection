# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary modules.
### Step2:
For performing edge detection on a image use sobel,canny laplacian operations.

### Step3:
Display all the images with their respective edge detected images.
 
## Program:

``` Python
# Import the packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image, Convert to grayscale and remove noise
img=cv2.imread("world.jpg")
img=cv2.resize(img,(500,400))
g_img=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original image",img)
cv2.imshow("Gray image",g_img)
cv2.waitKey(0)
cv2.destroAllWindows()
img1=cv2.GaussianBlur(g_img,(3,3),0)
cv2.imshow("Gaussian Blur",img1)
cv2.waitKey(0)
cv2.destroyAllWindows()

# SOBEL EDGE DETECTOR
sobelx = cv2.Sobel(img1,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(img1,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(img1,cv2.CV_64F,1,1,ksize=5)
plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(img1)
plt.title('Original'), plt.xticks([]), plt.yticks([])

plt.subplot(2,2,2)
plt.imshow(sobelx)
plt.title('sobelx')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,3)
plt.imshow(sobely)
plt.title('sobely')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,4)
plt.imshow(sobelxy)
plt.title('sobelxy')
plt.xticks([]), plt.yticks([])
plt.show()

# LAPLACIAN EDGE DETECTOR
lap=cv2.Laplacian(img1,cv2.CV_64F)
cv2.imshow("Laplacian edge detector",lap)
cv2.waitKey(0)
cv2.destroyAllWindows()

# CANNY EDGE DETECTOR
canny = cv2.Canny(img1, 70, 150)
cv2.imshow("Canny edge detector",canny)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## <br><br><br><br><br><br><br><br>Output:
### <br><br><br><br>SOBEL EDGE DETECTOR
![Screenshot (175)](https://user-images.githubusercontent.com/75243072/173771860-3d3527f2-750b-460c-a844-b00c3e9e8351.png)

### <br><br><br><br>LAPLACIAN EDGE DETECTOR
![Screenshot (176)](https://user-images.githubusercontent.com/75243072/173771944-66dbfdf0-01ab-46ad-9097-05aaac5c1006.png)

### <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>CANNY EDGE DETECTOR
![Screenshot (177)](https://user-images.githubusercontent.com/75243072/173772157-9a474982-f2ab-41ef-8025-a2e7c0fe8321.png)


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
