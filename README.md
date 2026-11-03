# Exp-8-Record-THRESHOLDING

## Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program

~~~python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read image
img = cv2.imread('img.jpg')

# Convert to grayscale
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# Global Thresholding
_, global_thresh = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

# Adaptive Mean Thresholding
mean_thresh = cv2.adaptiveThreshold(
    gray, 255, cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY, 11, 2
)

# Adaptive Gaussian Thresholding
gaussian_thresh = cv2.adaptiveThreshold(
    gray, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY, 11, 2
)

# Otsu's Thresholding
_, otsu_thresh = cv2.threshold(
    gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

# Display results
images = [gray, global_thresh, mean_thresh,
          gaussian_thresh, otsu_thresh]

titles = ['Grayscale', 'Global Threshold',
          'Adaptive Mean', 'Adaptive Gaussian',
          "Otsu's Threshold"]

plt.figure(figsize=(12, 8))

for i in range(5):
    plt.subplot(2, 3, i+1)
    plt.imshow(images[i], cmap='gray')
    plt.title(titles[i])
    plt.axis('off')

plt.tight_layout()
plt.show()
~~~

## Developed By

**Name:** Aman Nair

**Register No:** 212225240008

## Output

### Original Grayscale Image

<img width="377" height="556" alt="image" src="https://github.com/user-attachments/assets/6bd40216-54e3-4aa3-aca5-d15fe79c9db4" />

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.

### Global Thresholding

<img width="413" height="546" alt="image" src="https://github.com/user-attachments/assets/966286ae-4ca2-46da-b883-1148fc5b3ac2" />


- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

### Adaptive Thresholding

<img width="410" height="582" alt="image" src="https://github.com/user-attachments/assets/a1802e2d-850a-42fc-8b0c-8950ab9a8e3e" />
<img width="382" height="585" alt="image" src="https://github.com/user-attachments/assets/28073728-ec3c-49ec-b787-8c8a4d872051" />


- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.

### Otsu's Thresholding

<img width="409" height="587" alt="image" src="https://github.com/user-attachments/assets/52e71ccd-90ee-4c6a-b596-938f8fd13432" />


- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.


## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 
