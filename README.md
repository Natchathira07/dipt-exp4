# dipt-exp4
## Geometric Transformations Using OpenCV

### Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

##  Program

### Developed By: VD Natchathira
### Register No: 212224230178
### ORIGINAL IMAGE:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("C:/Users/admin/Pictures/Screenshots/Screenshot 2026-08-08 205530.png")
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off')
```
### TRANSLATED IMAGE:
```
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Translated Image")  
plt.axis('off')
```
### SCALED IMAGE:
```
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  # Set title
plt.axis('off')
```
### SHEARED IMAGE:
```
shear_matrix = np.float32([[0.5, 1, 0], [0, 0.5, 1]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')
```
### REFLECTED IMAGE:
```
reflected_image = cv2.flip(image, 2)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image") 
plt.axis('off')
```
### ROTATED IMAGE:
```
(height, width) = image.shape[:2] 
angle = 45  
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) 
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image")  
plt.axis('off')
```
### CROPPED IMAGE:
```
x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image") 
plt.axis('off')
```
##  Output

<img width="441" height="296" alt="image" src="https://github.com/user-attachments/assets/4189ab58-1897-4dd5-b663-44cc82d53705" />


<img width="437" height="297" alt="image" src="https://github.com/user-attachments/assets/1ee65c70-82f9-4a7d-b778-d037bd88cd4d" />


<img width="442" height="133" alt="image" src="https://github.com/user-attachments/assets/84a37bae-944b-4687-853c-243d49c723db" />


<img width="438" height="295" alt="image" src="https://github.com/user-attachments/assets/66aa119b-c6f3-4055-b86c-4d2e6ce84082" />


<img width="437" height="301" alt="image" src="https://github.com/user-attachments/assets/48ce1177-23e9-4d6c-89be-29d974e268e5" />


<img width="436" height="301" alt="image" src="https://github.com/user-attachments/assets/15d8a0d6-193b-4e70-a9b1-4d49c37b6a02" />


<img width="440" height="353" alt="image" src="https://github.com/user-attachments/assets/0f0531f7-c610-4c1c-a1d6-504c3bd1a9d1" />

## Result 
Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
