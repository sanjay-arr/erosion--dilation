# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Initialize an Empty Image:Create a black image of size 100x600 pixels.

### Step2:
Add Text to the Image:Use a specified font to write the word "Lifestyle" on the image at a defined position.

### Step3:
Display the Original Image:Show the image containing the text without axis labels.

### Step4:
Create Structuring Elements:Define a structuring element for morphological operations (e.g., a cross-shaped kernel).

### Step5:
Erode the Image:Apply erosion to the image using the defined structuring element to reduce the size of white regions. ### Step-6 Dilate the Image:Apply dilation to the original image using the same structuring element to increase the size of white regions.

## Program:

``` Python
Developed by : G Sanjay
Register Number : 212224230243
```
# Import the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
# Create the Text using cv2.putText
```
image = np.zeros((300, 600, 3), dtype="uint8")
text = "JACK"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.subplot(1, 1, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
```
# Create the structuring element
```
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
```
# Erode the image
```
eroded_image = cv2.erode(image, kernel, iterations=1)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
plt.subplot(1, 1,1)
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")
```
# Dilate the image
```
dilated_image = cv2.dilate(image, kernel, iterations=1)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)
plt.subplot(1, 1,1)
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")
```
## Output:

### Display the input Image
<img width="785" height="486" alt="image" src="https://github.com/user-attachments/assets/806f1ea2-1002-47ac-afa6-2d845bd2c3ab" />

### Display the Eroded Image
<img width="647" height="362" alt="image" src="https://github.com/user-attachments/assets/3d493d83-9efd-4ded-baf1-97b686c5cc76" />

### Display the Dilated Image
<img width="642" height="361" alt="image" src="https://github.com/user-attachments/assets/46c2edd7-1f66-46f7-9145-4bf550c3eecb" />

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
