# Canny-Edge-Detection


## Aim
To implement the Canny Edge Detection algorithm on a sample image using Python and OpenCV to detect and extract edges.

## Software Requirements
- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## Algorithm
1. Read the input image.
2. Convert the image into grayscale.
3. Apply Gaussian Blur to remove noise.
4. Apply the Canny Edge Detection algorithm.
5. Display the original and detected edge images.
6. Change threshold values and compare the results.

## Program
### Developed by
#### Name: MADHUMITHA R R
#### Reg no: 212224240083

```python
import cv2
import matplotlib.pyplot as plt

# Read input image
img = cv2.imread('sample.jpg')

# Convert to grayscale
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# Apply Gaussian Blur
blur = cv2.GaussianBlur(gray, (5, 5), 0)

# Apply Canny Edge Detection
edges = cv2.Canny(blur, 100, 200)

# Display images
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

plt.show()
```

## Discussion of Detected Edges

Canny Edge Detection identifies the boundaries of objects in an image.

The algorithm involves five main steps:

1. **Noise Reduction:** Gaussian Blur removes unwanted noise.
2. **Gradient Calculation:** Identifies changes in image intensity.
3. **Non-Maximum Suppression:** Makes detected edges thinner.
4. **Double Thresholding:** Classifies pixels into strong, weak and non-edge pixels.
5. **Edge Tracking by Hysteresis:** Connects relevant weak edges to strong edges and removes unwanted edges.

### Observation
- Object boundaries are detected clearly.
- Strong edges appear white.
- Background regions appear black.
- Small details and object outlines can be identified.

## Effect of Different Parameter Settings

The Canny algorithm uses two main threshold values: Lower Threshold and Upper Threshold.

| Threshold Values | Effect |
|---|---|
| 30, 100 | Detects more edges, including small details and noise. |
| 100, 200 | Produces balanced edge detection. |
| 150, 250 | Detects fewer edges and focuses on strong boundaries. |

### Comparison Code

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread('sample.jpg', 0)

blur = cv2.GaussianBlur(img, (5, 5), 0)

edge1 = cv2.Canny(blur, 30, 100)
edge2 = cv2.Canny(blur, 100, 200)
edge3 = cv2.Canny(blur, 150, 250)

plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(edge1, cmap='gray')
plt.title('Threshold: 30, 100')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(edge2, cmap='gray')
plt.title('Threshold: 100, 200')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(edge3, cmap='gray')
plt.title('Threshold: 150, 250')
plt.axis('off')

plt.show()
```

### Parameter Observation
- **Low Threshold:** Detects more edges, including weak edges and noise.
- **Medium Threshold:** Provides a balanced result with clear boundaries.
- **High Threshold:** Detects fewer edges and removes many weak edges.
- **Gaussian Kernel Size:** A larger kernel removes more noise but may eliminate small details.

## Output

<img width="600" height="381" alt="image" src="https://github.com/user-attachments/assets/b662151b-a619-46c0-aa09-516032fb0011" />


## Result

Thus, the Canny Edge Detection algorithm was successfully implemented using Python and OpenCV. Edges were detected from the sample image, and the effects of different threshold values were studied.
