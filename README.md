# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** Chowla Chaithanya 

### Register No: 2305002004  
1. import libraries.
```
import cv2
import matplotlib.pyplot as plt

```
2. Read grayscale image.
```
plt.figure(figsize=(6,6))
plt.imshow(Gray_image, cmap='gray')
plt.title("Gray Scale Image")
plt.axis("off")
plt.show()

```

3. Display Gray Scale Image.
```
Color_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.32.43.jpeg")

```
4. Read color image.
```
Color_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.32.43.jpeg")

```
5. Convert BGR to RGB.
```
Color_rgb = cv2.cvtColor(Color_image, cv2.COLOR_BGR2RGB)

```
6. Display Color Image.
```
plt.figure(figsize=(6,6))
plt.imshow(Color_rgb)
plt.title("Color Image")
plt.axis("off")
plt.show()

```
7. Histogram of Gray Scale Image.
```
hist_gray = cv2.calcHist([Gray_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Gray Scale Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_gray, color='black')
plt.xlim([0,256])
plt.show()

```
8. Histogram of Blue Channel.
```
hist_blue = cv2.calcHist([Color_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Blue Channel")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_blue, color='blue')
plt.xlim([0,256])
plt.show()

```
9. Histogram Equalization.
```
equalized = cv2.equalizeHist(Gray_image)
```
10. Histogram of Equalized Image.
```
hist_equalized = cv2.calcHist([equalized], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Equalized Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_equalized, color='green')
plt.xlim([0,256])
plt.show()
```
##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed

<img width="518" height="365" alt="{7A667B08-055C-4727-A56C-34C0275E522D}" src="https://github.com/user-attachments/assets/3c7595be-cac9-499f-a850-5196133a78e6" />

- Histogram of original grayscale image is plotted


<img width="553" height="345" alt="{40C0DDD5-7FB7-4A5F-8FD0-BC5AF2BCFA36}" src="https://github.com/user-attachments/assets/82ccf524-d35a-47f1-81d2-9b1aa113fd9c" />

- Enhanced image after histogram equalization is displayed
 
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed


<img width="463" height="324" alt="{25A669F7-204F-462A-A456-BDF9306DF38A}" src="https://github.com/user-attachments/assets/67f12fae-6075-482a-99b8-ff748a7447e9" />
 
- Histogram of B, G, R channels is plotted


<img width="504" height="274" alt="{66A7FF4C-EEE0-4FFB-9C52-5E3D95998F8A}" src="https://github.com/user-attachments/assets/50044d9b-877a-47eb-adb4-2e88ad334ae5" />

- Enhanced image after HSV-based equalization is displayed
 
- Histogram of enhanced image shows better intensity distribution


<img width="523" height="413" alt="{FC8F2B97-B56A-4606-B785-68404115EBDC}" src="https://github.com/user-attachments/assets/262ee685-caad-4664-b915-279c550876b4" />
 

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
