# Opening and Closing Operations Using OpenCV
## Aim
To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

Morphological Opening
Morphological Closing
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Create or load an input image containing foreground objects.

Step 3:
Display the original image.

Step 4:
Create a structuring element (kernel) of suitable size.

Step 5: Opening Operation
Apply the Opening operation using the structuring element.
Opening consists of Erosion followed by Dilation.
Remove small foreground noises while preserving the shape of larger objects.
Display the opened image.

Step 6: Closing Operation
Apply the Closing operation using the structuring element.
Closing consists of Dilation followed by Erosion.
Fill small holes and gaps within foreground objects.
Display the closed image.

Step 7:
Compare the original, opened, and closed images.

## Program
#### Developed By
#### Name: KALPESH C
#### Register No: 212225230121
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)
# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Open and Close', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
```

```
# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)
# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
```

```
# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
```
## Output

<img width="391" height="406" alt="image (1)" src="https://github.com/user-attachments/assets/72834c52-7a5c-4e68-bbc7-5c06a9b085b4" />


#### Original Image
- The input image is displayed.

- The image serves as the source for morphological processing. 

#### Opening Operation
- Original image is displayed.

- Opened image is displayed.

- Small foreground noise is removed.

- Thin protrusions and isolated pixels are eliminated.

- Object boundaries become smoother.

#### Closing Operation
- Original image is displayed.

- Closed image is displayed.

- Small holes and gaps inside objects are filled.

- Broken regions are connected.

- Object boundaries become more continuous.

### Applications
#### Opening
- Noise removal in binary images.

- Separation of connected objects.

- Preprocessing for object detection.

#### Closing
- Filling small holes in objects.

- Connecting nearby components.

- Enhancing segmented regions.

### Advantages
#### Opening
- Removes unwanted foreground noise.

- Preserves major object structures.

- Improves segmentation quality.

#### Closing
- Restores object continuity.

- Eliminates small background gaps.

- Improves object representation.

## Result
Thus, the morphological operations Opening and Closing are successfully implemented using OpenCV.
