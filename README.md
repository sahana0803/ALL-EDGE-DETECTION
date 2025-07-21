# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Code :

## Original:
```
import cv2
import numpy as np

# Load the image
image = cv2.imread('exp6img.jpeg')  # Replace with your image path
if image is None:
    raise ValueError("Image not found. Check the file path.")

# Convert to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
## SOBEL EDGE DETECTOR
```
# Detect edges in X and Y directions
sobelx = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)
sobely = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)
sobel_combined = cv2.magnitude(sobelx, sobely)
sobel_combined = cv2.convertScaleAbs(sobel_combined)
```
## LAPLACIAN EDGE DETECTOR
```
laplacian = cv2.Laplacian(gray, cv2.CV_64F)
laplacian = cv2.convertScaleAbs(laplacian)
```
## CANNY EDGE DETECTOR
```
canny = cv2.Canny(gray, 100, 200)  # Adjust thresholds as needed  
```

## DISPLAY RESULTS
```
cv2.imshow('Original', image)
cv2.imshow('Sobel X', cv2.convertScaleAbs(sobelx))
cv2.imshow('Sobel Y', cv2.convertScaleAbs(sobely))
cv2.imshow('Sobel Combined', sobel_combined)
cv2.imshow('Laplacian', laplacian)
cv2.imshow('Canny', canny)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:

## Original:

![Screenshot 2025-04-25 035615](https://github.com/user-attachments/assets/1f219436-ae76-461c-8108-43e776667197)



### SOBEL EDGE DETECTOR:

![Screenshot 2025-04-25 035831](https://github.com/user-attachments/assets/4b56c33a-9eb0-40ad-8a29-6b5159edb19d)


### LAPLACIAN EDGE DETECTOR:

![Screenshot 2025-04-25 035849](https://github.com/user-attachments/assets/4a33e21f-3113-4d8f-9f71-cff8edf5526b)


### CANNY EDGE DETECTOR

![Screenshot 2025-04-25 035910](https://github.com/user-attachments/assets/05f1c902-36ce-4db6-9566-ccd0c21b6df1)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
