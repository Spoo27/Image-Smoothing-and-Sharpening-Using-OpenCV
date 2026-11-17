# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By
## Name: Spoorthi V 
## Register No: 212224230271

---
## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("Qno. 1.jpeg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
plt.show()

avg = cv2.blur(img, (5,5))
plt.imshow(avg)
plt.title("Averaging Filter")
plt.axis("off")
plt.show()

kernel = np.array([[1,2,1],
                 [2,4,2],
                 [1,2,1]], np.float32) / 16
weighted = cv2.filter2D(img, -1, kernel)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis("off")
plt.show()

gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()

median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()

kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)<img width="572" height="451" alt="Screenshot 2026-11-16 220339" src="https://github.com/user-attachments/assets/4bf8faf6-6b4a-40b8-80b4-23c2e061acc9" />

plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

##  Output

<img width="587" height="452" alt="Screenshot 2026-11-16 220326" src="https://github.com/user-attachments/assets/baf9fe56-9046-45bd-bea3-5d278f33fa53" />

<img width="572" height="451" alt="Screenshot 2026-11-16 220339" src="https://github.com/user-attachments/assets/895fa948-a4af-4111-8d39-46e965f91224" />

<img width="563" height="447" alt="Screenshot 2026-11-16 220540" src="https://github.com/user-attachments/assets/bf207cd0-db04-457a-8f03-5cba7d75f4aa" />

<img width="580" height="453" alt="Screenshot 2026-11-16 220553" src="https://github.com/user-attachments/assets/ca9521e0-5b65-4791-a138-e51a2d55a5aa" />

<img width="586" height="441" alt="Screenshot 2026-11-16 220603" src="https://github.com/user-attachments/assets/880098a7-d175-4ad0-b4ac-9d4beef5fb30" />

<img width="562" height="450" alt="Screenshot 2026-11-16 220619" src="https://github.com/user-attachments/assets/4eda9152-c8cc-4feb-ab57-78a58e504aa7" />

<img width="577" height="448" alt="Screenshot 2026-11-16 220629" src="https://github.com/user-attachments/assets/e95367e4-a4b3-42ee-9aa5-3890028d5413" />

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
