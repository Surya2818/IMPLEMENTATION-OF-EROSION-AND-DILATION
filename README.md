# Implementation of Erosion and Dilation Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological operations such as Erosion and Dilation on an image.

The program performs the following operations:

* Image Erosion
* Image Dilation

## Software Used

* Anaconda – Python 3.7 (or higher)
* Jupyter Notebook / VS Code
* OpenCV (`cv2`)
* NumPy
* Matplotlib

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Create a blank black image (`500 x 500`) using NumPy.

### Step 3:
Insert white text onto the blank image using OpenCV's `cv2.putText()` drawing function.

### Step 4:
Display the original image using Matplotlib.

### Step 5:
Create a structuring element (kernel) of size `3 x 3` using `np.ones()`.

### Step 6: Image Erosion
* Apply the erosion operation (`cv2.erode()`) using the created kernel.
* Remove pixels from the boundaries of foreground objects (white text).
* Display the eroded image.

### Step 7: Image Dilation
* Apply the dilation operation (`cv2.dilate()`) using the same kernel.
* Add pixels to the boundaries of foreground objects (white text).
* Display the dilated image.

### Step 8:
Compare the original, eroded, and dilated images.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/1d8a8dfc-9486-4da9-95ed-6e2efcfbc229" />


# Step 2: Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Step 3: Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'SANTHOSE AROCKIRAJ J', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Step 4: Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
plt.show()

# Step 5: Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Step 6: Apply erosion (shrinking effect)
eroded_image = cv2.erode(image, kernel, iterations=1)

# Display the eroded image
plt.imshow(cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Eroded Image")
plt.axis('off')
plt.show()

# Step 7: Apply dilation (expanding effect)
dilated_image = cv2.dilate(image, kernel, iterations=1)

# Display the dilated image
plt.imshow(cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Dilated Image")
plt.axis('off')
plt.show()
```

## Developed By

* **Name:** SURYA D
* **Register No:** 212224220115

## Output

### Original Image
* A black canvas (`500 x 500`) containing white text (`SANTHOSE AROCKIRAJ J`) is displayed.
* Serves as the baseline input for morphological processing.

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/9d9504a4-6bf8-4bc3-9b93-62ec773a3b29" />


### Erosion
* The eroded image is displayed after applying a `3 x 3` kernel for 1 iteration.
* The stroke thickness of the characters is noticeably reduced as foreground boundaries shrink inward.

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/ad58dbea-58cb-45f0-9023-e57d4719eb6d" />


### Dilation
* The dilated image is displayed after applying a `3 x 3` kernel for 1 iteration.
* The stroke thickness of the characters increases and looks bolder as foreground boundaries expand outward.

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/e133f383-8c2d-40e9-82de-9526ea7d683e" />


## Result

Thus, the morphological operations **Erosion** and **Dilation** are successfully implemented using OpenCV.
