# DIPT-WORKSHOP-4
# Coin-Detection-using-OpenCV-in-Python
## Name : Jones Benedict A P
## Reg.no : 21224040142

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread('CoinsA.png')
imageCopy = image.copy()
plt.imshow(image[:,:,::-1]);
plt.title("Original Image")
plt.show()
plt.figure(figsize=(12,12))
plt.subplot(121);plt.imshow(image[:,:,::-1]);plt.title("Original Image")
plt.subplot(122); plt.imshow(imageGray,cmap='gray');plt.title("Grayscale Image"); plt.show()
plt.figure(figsize=(20,12))
plt.subplot(141);plt.imshow(image[:,:,::-1]);plt.title("Original Image")
plt.subplot(142);plt.imshow(imageB,cmap='gray');plt.title("Blue Channel")
plt.subplot(143);plt.imshow(imageG,cmap='gray');plt.title("Green Channel")
plt.subplot(144);plt.imshow(imageR,cmap='gray');plt.title("Red Channel");
plt.show()
thresh =20
maxValue = 255
th, dst_bin_inv = cv2.threshold(imageG, thresh, maxValue, cv2.THRESH_BINARY_INV)
plt.imshow(dst_bin_inv, cmap='gray', vmin=0, vmax=255)
plt.title("Threshold Binary Inverse");
kSize = (5,5)
kernel2 = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, kSize)
imageDilated2 = cv2.dilate(dst_bin_inv, kernel2, iterations=2)
plt.imshow(imageDilated2,cmap='gray')
plt.title('Dilated Image Iteration 2')
plt.show()
kSize = (11,11)
kernel1 = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, kSize)
imageEroded = cv2.erode(imageDilated2, kernel1)
plt.imshow(imageEroded,cmap='gray')
plt.title("Eroded Image")
plt.show()
# Set up the SimpleBlobdetector with default parameters.
params = cv2.SimpleBlobDetector_Params()

params.blobColor = 0

params.minDistBetweenBlobs = 2

# Filter by Area.
params.filterByArea = False

# Filter by Circularity
params.filterByCircularity = True
params.minCircularity = 0.8

# Filter by Convexity
params.filterByConvexity = True
params.minConvexity = 0.8

# Filter by Inertia
params.filterByInertia =True
params.minInertiaRatio = 0.8

```


<img width="714" height="563" alt="image" src="https://github.com/user-attachments/assets/912f3844-af73-459d-930a-8ee859e8743c" />
<img width="1333" height="680" alt="image" src="https://github.com/user-attachments/assets/f2be369a-35b7-466c-97de-9da2a7a3b4e8" />
<img width="1383" height="381" alt="image" src="https://github.com/user-attachments/assets/35f99c51-8cdc-4378-af2a-db8ea372f803" />
<img width="758" height="570" alt="image" src="https://github.com/user-attachments/assets/044732a9-3403-4b30-9f57-c1e214730631" />
<img width="776" height="548" alt="image" src="https://github.com/user-attachments/assets/d2d508d0-035a-4dde-9b54-b94b2b7b5036" />
<img width="614" height="545" alt="image" src="https://github.com/user-attachments/assets/1641d932-76a2-4fed-acd0-677cfc52fa62" />
