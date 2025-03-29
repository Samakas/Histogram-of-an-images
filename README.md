# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: Samakash R S
# Register Number: 212223230182
```
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Get the input grayscale image
gray_image = cv2.imread('Qn3_Histogram_Bright_Image.tif', cv2.IMREAD_GRAYSCALE)

# Step 2: Display the grayscale image
plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')

# Step 3: Plot the histogram of the grayscale image
plt.subplot(2, 2, 3)
plt.plot(gray_image.ravel(), color='black')
plt.title('Original Histogram')
plt.xlim([0, 256])

# Step 4: Apply histogram equalization using OpenCV
equalized_gray_image = cv2.equalizeHist(gray_image)

# Step 5: Display the histogram of the equalized image
plt.subplot(2, 2, 4)
hist_equalized = cv2.calcHist([equalized_gray_image], [0], None, [256], [0, 256])
plt.plot(equalized_gray_image.ravel(), color='black')
plt.title('Equalized Histogram')
plt.xlim([0, 256])


# Step 1: Get the input color image
color_image = cv2.imread('boy.jpg')
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')

# Step 3: Plot the histogram of the input color image (combined channels)
# Calculate the histogram for all channels separately
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])

# Plot the histograms
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
```
## Output:
### Input Grayscale Image and Color Image


### Histogram of Grayscale Image and any channel of Color Image



### Histogram Equalization of Grayscale Image.




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
