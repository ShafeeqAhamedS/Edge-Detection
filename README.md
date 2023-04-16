# Edge-Detection
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
plt.imshow(laplacian,cmap = 'gray')
plt.title('laplacian')
plt.axis("off")
plt.show()
```

### CANNY EDGE DETECTOR
```py
canny_edges = cv2.Canny(img, 120, 150)
plt.imshow(canny_edges)
plt.title('canny_edges')
plt.axis("off")
plt.show()
```

## Output:
### SOBEL EDGE DETECTOR

| Format   | Tag example |
| -------- | ----------- |
|  ![image](https://user-images.githubusercontent.com/93427237/232279968-41d8eb6c-f252-457b-9799-85759de105de.png) |  ![image](https://user-images.githubusercontent.com/93427237/232280105-a11ce40f-50ee-4c35-954f-7634d231ee49.png) |
| ![image](https://user-images.githubusercontent.com/93427237/232280133-88085951-9edf-4ef8-9862-f2470f0464f6.png) |  ![image](https://user-images.githubusercontent.com/93427237/232280145-b79b2a0c-83ed-48b8-aa25-1928fbfe1720.png) |


### LAPLACIAN EDGE DETECTOR



### CANNY EDGE DETECTOR


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
