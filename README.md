# EXPERIMENT 10 – IMPLEMENTATION OF OPENING AND CLOSING
## Name : Raha Priya Dharshini M
## Reg No.: 212224240124

## Aim
To implement morphological operations such as Opening and Closing on an image using OpenCV and Python.

## Software Requirements
- Python
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook

## Procedure

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Create a blank image of size 500 × 500 using NumPy.
3. Add text to the image using the `cv2.putText()` function.
4. Create a 3 × 3 kernel using `np.ones()`.
5. Display the input image containing text.
6. Apply the **Opening Operation** using `cv2.morphologyEx()` with `cv2.MORPH_OPEN`. Opening performs erosion followed by dilation.
7. Display the resulting image after the Opening operation.
8. Apply the **Closing Operation** using `cv2.morphologyEx()` with `cv2.MORPH_CLOSE`. Closing performs dilation followed by erosion.
9. Display the resulting image after the Closing operation.
10. Compare the input image and the results of both morphological operations.

## Code
```

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text to the image
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(
    image,
    'Raha Priya D',
    (100, 250),
    font,
    1,
    (255, 255, 255),
    2,
    cv2.LINE_AA
)

# Create a 3x3 kernel
kernel = np.ones((3, 3), np.uint8)

# Display the input image
plt.figure(figsize=(7, 6))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image with Text")
plt.axis('off')
plt.show()

# Apply Opening (Erosion followed by Dilation)
opened_image = cv2.morphologyEx(
    image,
    cv2.MORPH_OPEN,
    kernel
)

# Display Opening result
plt.figure(figsize=(7, 6))
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))
plt.title("Opening Operation")
plt.axis('off')
plt.show()

# Apply Closing (Dilation followed by Erosion)
closed_image = cv2.morphologyEx(
    image,
    cv2.MORPH_CLOSE,
    kernel
)

# Display Closing result
plt.figure(figsize=(7, 6))
plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))
plt.title("Closing Operation")
plt.axis('off')
plt.show()
```
## Output

### 1. Input Image with Text
<img width="1380" height="555" alt="image" src="https://github.com/user-attachments/assets/03a44fe9-c58c-402e-8d3a-979e44b89eaf" />


### 2. Opening Operation
<img width="1351" height="542" alt="image" src="https://github.com/user-attachments/assets/06045eb2-0c0c-45d0-9a96-62727fd8fcb4" />


### 3. Closing Operation
<img width="1373" height="632" alt="image" src="https://github.com/user-attachments/assets/758a1425-a0d9-425a-8f70-7c42a4cc1e97" />


## Result
Thus, the morphological operations of Opening and Closing were successfully implemented using OpenCV and Python.
