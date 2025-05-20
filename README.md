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

## Program:
### Developed by: Krithick Vivekananda 
### Register no: 212223240075

#### (i) Display the original image
```python
import cv2
import matplotlib.pyplot as plt
image = cv2.imread("Lion.png")  
# Convert BGR to RGB for correct color display
rgb_image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Convert BGR to Grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Display both images side by side
plt.figure(figsize=(10, 5))
# Original image
plt.subplot(1, 2, 1)
plt.imshow(rgb_image)
plt.title('Original Image')
plt.axis('off')
# Grayscale image
plt.subplot(1, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```

#### (ii) Apply Sobel Edge Detection
```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
# Display Sobel Edge Detection
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
plt.show()
```

#### (iii) Apply Laplacian Edge Detection
```python
# Apply Laplacian edge detector
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
# Display Laplacian Edge Detection
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()
```

#### (iv) Apply Canny Edge Detection
```python
canny_edges = cv2.Canny(gray_image, 50, 150)
# Display Canny Edge Detection
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
plt.show()
```

## Output:

### ORIGINAL AND GRAYSCALE IMAGE
![image](https://github.com/user-attachments/assets/ccc54282-5681-42fe-b364-57395048e8e1)

### SOBEL EDGE DETECTOR
![image](https://github.com/user-attachments/assets/96fa1a20-0a01-41df-94d7-5dd6e0bd4902)

### LAPLACIAN EDGE DETECTOR
![image](https://github.com/user-attachments/assets/09151f55-fee2-4176-bebe-66a4f0548cdc)

### CANNY EDGE DETECTOR
![image](https://github.com/user-attachments/assets/8d1ecad0-b20d-4de0-8cfa-7b70b9dbd89b)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
