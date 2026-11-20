# Exp-7-Record-HOUGH-TRANSFORM

## Name: Renick Fabian Rajesh
## Reg No: 212224230227

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

## Program: 

```

import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('dp.jpg')  # Replace 'image.jpg' with your image path

# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')

```

<img width="515" height="417" alt="image" src="https://github.com/user-attachments/assets/40c2b221-02ac-4129-b504-39d16bdf6a07" />

```

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

```

<img width="520" height="402" alt="image" src="https://github.com/user-attachments/assets/983abcc3-df15-4011-a1c6-11532ba976a5" />

```

# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150

# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

```

<img width="527" height="405" alt="image" src="https://github.com/user-attachments/assets/f458daf0-a26f-4a0f-8265-4809c50590a6" />

```

# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)


# Step 6: Draw the detected lines on the original image

# Reshape lines to get four coordinates (x1, y1, x2, y2)
for line in lines.reshape(-1, 4):
    x1, y1, x2, y2 = line

    # Draw green lines with thickness of 2
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

```

<img width="516" height="410" alt="image" src="https://github.com/user-attachments/assets/04ce1888-a856-416b-9cfb-d0840f35fc9c" />








## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---

