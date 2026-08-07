# Histogram Equalization Using OpenCV

## Name: MOHAMMED HAMZA M
## Reg No: 212224230167

## Aim

To improve the contrast of grayscale and color images using Histogram Equalization in OpenCV and compare the original and enhanced images along with their histograms.

---

# Software Used

- Python 3.x
- OpenCV (cv2)
- Matplotlib
- Jupyter Notebook

---

# Algorithm

1. Import the required libraries.
2. Load the input image.
3. Convert the image to grayscale.
4. Display the grayscale image.
5. Plot the histogram of the original grayscale image.
6. Apply Histogram Equalization to enhance the image contrast.
7. Display the equalized image and its histogram.
8. Load the original color image.
9. Convert the image from BGR to HSV color space.
10. Apply Histogram Equalization to the Value (V) channel.
11. Convert the HSV image back to the BGR color space.
12. Display the original and enhanced color images.
13. Compare the histograms before and after equalization.

---

# Program

## Step 1: Import Required Libraries

```python
import cv2
import matplotlib.pyplot as plt
```

---

## Step 2: Load the Grayscale Image

```python
img = cv2.imread('EAGLE.png', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Grayscale Image')
plt.show()
```

### Output

<img width="995" height="478" alt="image" src="https://github.com/user-attachments/assets/cfd89566-dcbb-49c5-84fc-36cf21b7fda1" />


---

## Step 3: Display the Histogram of the Original Image

```python
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')
plt.show()
```

### Output

<img width="983" height="528" alt="image" src="https://github.com/user-attachments/assets/a34afca9-f48d-46f1-8c64-1e88d77a6ce1" />


---

## Step 4: Apply Histogram Equalization

```python
img_eq = cv2.equalizeHist(img)
```

---

## Step 5: Display the Equalized Histogram

```python
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```

### Output

 <img width="987" height="546" alt="image" src="https://github.com/user-attachments/assets/1c76bbc3-ab86-4148-aa8a-43efd1aad8a3" />


---

## Step 6: Display the Equalized Grayscale Image

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```

### Output

<img width="990" height="477" alt="image" src="https://github.com/user-attachments/assets/db77f91d-ed17-464f-b61c-b044e1759486" />


---

## Step 7: Load the Color Image

```python
img = cv2.imread('EAGLE.png', cv2.IMREAD_COLOR)
```

---

## Step 8: Convert the Image to HSV Color Space

```python
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```

---

## Step 9: Equalize the Value (V) Channel

```python
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```

---

## Step 10: Convert Back to BGR

```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```

---

## Step 11: Compare the Original and Enhanced Color Images

```python
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```

### Output

<img width="892" height="471" alt="image" src="https://github.com/user-attachments/assets/0eabd449-5c1c-4ad5-a935-dad29b5d3fb1" />


---

## Step 12: Compare Images and Histograms

```python
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

### Output

<img width="1032" height="692" alt="image" src="https://github.com/user-attachments/assets/045f21c3-19c3-4d5e-9c79-2972de5a5724" />


---

# Result

Histogram Equalization was successfully applied to both grayscale and color images using OpenCV. The technique enhanced the image contrast by redistributing the pixel intensity values, resulting in improved visual quality. A comparison of the original and equalized images, along with their corresponding histograms, demonstrates the effectiveness of the enhancement process.
