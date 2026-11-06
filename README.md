# Ex. No: 5 – Implementation of Filters
### Developed By : LOKESH S
### Register Number : 2122242400479
### Aim :
To implement various image filtering techniques using Python and OpenCV to smooth images, reduce noise, and enhance image details.
### Requirements :
Hardware Requirements:
- Computer or Laptop
- Minimum 4 GB RAM
Software Requirements:
- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib
### Procedure :
1. Import the required libraries such as OpenCV, NumPy, and Matplotlib.
2. Read the input image using cv2.imread().
3. Convert the image from BGR to RGB format.
4. Apply an Average Filter using a predefined kernel.
5. Apply a Weighted Average Filter to smooth the image.
6. Apply a Gaussian Filter to reduce image noise.
7. Apply a Median Filter to remove noise while preserving edges.
8. Apply a Laplacian Kernel to highlight image details.
9. Apply the Laplacian Operator to detect edges.
10. Display the original and filtered images using Matplotlib.

### Program : 
```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("ex.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("on")
plt.show()
```
```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("on")
plt.show()
```
```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("on")
plt.show()
```
```python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("on")
plt.show()
```
```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("on")
plt.show()
```
```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("on")
plt.show()
```

### Output : 
<img width="743" height="460" alt="image" src="https://github.com/user-attachments/assets/30f0a80e-eb56-4e23-a995-0e03fbdb7c54" />


<img width="565" height="345" alt="image" src="https://github.com/user-attachments/assets/9cdb6556-25ff-447c-a44f-403968fbbb52" />

<img width="543" height="340" alt="image" src="https://github.com/user-attachments/assets/0aea6730-2bcf-4528-b305-d1d22dd00728" />

<img width="764" height="467" alt="image" src="https://github.com/user-attachments/assets/9c02458d-ffb5-4d6e-a3ca-0b3132c666be" />


<img width="536" height="354" alt="image" src="https://github.com/user-attachments/assets/4c05e781-fb48-4088-8104-7cb1c20d6d41" />

<img width="522" height="334" alt="image" src="https://github.com/user-attachments/assets/dd0e1c60-6ecb-4b58-b667-43cd9ca970be" />


### Result :
Thus, various image filtering techniques such as Average Filter, Weighted Average Filter, Gaussian Blur, Median Blur, and Laplacian Operator were successfully implemented using Python and OpenCV. The filtered images were displayed and their effects were observed.
