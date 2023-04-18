# <p align="center"> Edge-Detection </p>
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the necessary modules.

### Step 2:
Perform edge detection on a image. 
- Sobel 
- Laplacian
- Canny

### Step 3:
Display the original images with edge detected images.

 
## Program:


### Import the packages
```py
import cv2
from cv2 import COLOR_BGR2GRAY
import matplotlib.pyplot as plt
```

### Load the image, Convert to grayscale and remove noise
```py
input_img = cv2.imread("mikasa.jpg",1)

gray = cv2.cvtColor(input_img,COLOR_BGR2GRAY)

img = cv2.GaussianBlur(gray,(3,3),0)

cv2.imshow("GaussianBlur",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### SOBEL EDGE DETECTOR
```py
sobelx = cv2.Sobel(img,cv2.CV_64F,1,0,ksize=9)
sobely = cv2.Sobel(img,cv2.CV_64F,0,1,ksize=13)
sobelxy =cv2.Sobel(img,cv2.CV_64F,1,1,ksize=31)

plt.imshow(img,cmap = 'gray')
plt.title('Original')
plt.xticks([]), plt.yticks([])
plt.show()

plt.imshow(sobelx,cmap = 'gray')
plt.title('sobelx')
plt.xticks([]), plt.yticks([])
plt.show()

plt.imshow(sobely,cmap = 'gray')
plt.title('sobely')
plt.xticks([]), plt.yticks([])
plt.show()

plt.imshow(sobelxy,cmap = 'gray')
plt.title('sobelxy')
plt.xticks([]), plt.yticks([])

plt.show()
```
### LAPLACIAN EDGE DETECTOR
```py
laplacian = cv2.Laplacian(img,cv2.CV_64F)
cv2.imshow("laplacian",laplacian)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### CANNY EDGE DETECTOR
```py
canny_edges = cv2.Canny(img, 120, 150)
cv2.imshow("Canny",canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:
### SOBEL EDGE DETECTOR


| Original 	|  Sobel X	|
|:-:	|:-:	|
|  ![image](https://user-images.githubusercontent.com/93427237/232302426-19c23ff9-4ec3-4742-a490-5d162b5dd0a3.png)	| ![image](https://user-images.githubusercontent.com/93427237/232302405-717247d1-70b9-432c-b2b7-af633783c5ff.png) 	|
|  Sobel Y	| Sobel XY	|
|  ![image](https://user-images.githubusercontent.com/93427237/232302359-8a068533-af5c-4733-99e0-f7595e38b059.png)	| ![image](https://user-images.githubusercontent.com/93427237/232302274-442551d7-5aa0-43e9-a01d-4f3271c8ad56.png)|


### LAPLACIAN EDGE DETECTOR

| Original 	|  Laplacian |
|:-:	|:-:	|
|	![GaussianBlur](https://user-images.githubusercontent.com/93427237/232303603-1adb2755-9744-4876-b8d7-7912f5b6cba8.png) |	![laplacian](https://user-images.githubusercontent.com/93427237/232303583-650ce53e-1831-4e7b-9b4c-b2c2fabd3f38.png) |

### CANNY EDGE DETECTOR

| Original 	|  Canny Edge |
|:-:	|:-:	|
|	![GaussianBlur](https://user-images.githubusercontent.com/93427237/232303603-1adb2755-9744-4876-b8d7-7912f5b6cba8.png) |	![canny_edges](https://user-images.githubusercontent.com/93427237/232303844-ae2086aa-d3b9-4630-9365-d71c90dd2312.png) |

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
