# EXP-1-Image-Handling-and-Pixel-Transformations-Using-OpenCV

## AIM:

Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image.

Adjust the brightness of an image.

Modify the image contrast.

Generate a third image using bitwise operations.

## Software Required:

Anaconda - Python 3.7

Jupyter Notebook (for interactive development and execution)

## Algorithm:

Step 1:

Load an image from your local directory and display it.

Step 2:

Create a matrix of ones (with data type float64) to adjust brightness.

Step 3:

Create brighter and darker images by adding and subtracting the matrix from the original image.

Display the original, brighter, and darker images.

Step 4:

Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).

Display the original, lower contrast, and higher contrast images.

Step 5:

Split the image (boy.jpg) into B, G, R components and display the channels.

#  Program

### Name: S.DIVYA PRIYA

### Register Number: 212225240037

### Ex. No. 01
```

import cv2

import matplotlib.pyplot as plt
```

### Read the image using OpenCV
```

img = cv2.imread('photo 3.jpeg', cv2.IMREAD_COLOR)
```

### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
 ```

### Display the image using Matplotlib
```
plt.imshow(img_rgb, cmap='viridis')

plt.title("Original Image")

plt.axis('off')

plt.show()
```

### 1.Draw a line from the top-left to the bottom-right of the image

### Load the image
```

image = cv2.imread('photo 3.jpeg')

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape
```
### Draw a line from top-left to bottom-right
```
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)

plt.imshow(line_img, cmap='viridis')

plt.title("Image with Line")

plt.axis('off')

plt.show()
```

### 2.Draw a circle at the center of the image.
### Load the image
```

image = cv2.imread('photo 3.jpeg') 
```

### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(255,255,0),10)

cv2.circle(image, center, radius, color, thickness)

plt.imshow(circle_img, cmap='viridis')

plt.title("Image with Circle")

plt.axis('off')

plt.show()
```
### 3.Draw a rectangle around  the whole image
### Load the image
```
image = cv2.imread('photo 3.jpeg')
```

### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape
```
### Draw a rectangle around the Whole image
```

rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 255, 255), 10)  

plt.imshow(rectangle_img, cmap='viridis')

plt.title("Image with Rectangle")

plt.axis('off')

plt.show()
```

### 4.Add the text "OpenCV Drawing" at the top-left corner of the image.
### Load the image
```
image = cv2.imread('photo 3.jpeg')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

### Add text to the image
```

text_img = cv2.putText(img_rgb, "OpenCV Drawing", (50,100), cv2.FONT_HERSHEY_SIMPLEX, 3, (0, 255, 255), 10)

plt.imshow(text_img, cmap='viridis')

plt.title("IMAGE WITH TEXT")

plt.axis('off')

plt.show()
```

### 5.Convert the image from RGB to HSV,GRAY,YCrCb,RGB
### Load the image
```

image = cv2.imread('photo 3.jpeg')
      
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
### Original RGB Image
```
plt.imshow(image_rgb)

plt.title("Original RGB Image")

plt.axis("off")
```
### Convert RGB to HSV
```
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
```
### HSV Image') 
```
plt.imshow(image_hsv)

plt.title("HSV Image")

plt.axis("off")
```
### Convert RGB to GRAY
```

image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```

### Grayscale Image
```

plt.imshow(image_gray, cmap='gray')

plt.title("Grayscale Image")

plt.axis("off")
```

### Convert RGB to YCrCb
```

image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
### YCrCb Image
```
plt.imshow(image_ycrcb)

plt.title("YCrCb Image")

plt.axis("off")
```
### Convert HSV back to RGB
```
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)

plt.title("HSV to RGB Image")

plt.axis("off")
```

### Modify a block of pixels (300x300) to white, starting from (200, 200)
```
image[200:500, 200:500] = [255, 0, 255]  # Rows: 200-499, Columns: 200-499
```

### Convert BGR to RGB for displaying with Matplotlib
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
### Display the modified image
```
plt.imshow(image_rgb)

plt.title("Image with 300x300 White Block")

plt.axis("off")

plt.show()

```
###  6.Resize the original image to half its size and display it.

### Load the image
```
image = cv2.imread('photo 3.jpeg')

image.shape
```

### Resize the image to half its size
```

resized_image = cv2.resize(image, (768 // 2, 600 // 2)) 
```
### Convert BGR to RGB for displaying with Matplotlib
```
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

resized_image_rgb.shape
```

### Display the resized image
```
plt.imshow(resized_image_rgb)

plt.title("Resized Image (Half Size)")

plt.axis("off")

plt.show()
```
### Load the image
```
image = cv2.imread('photo 3.jpeg')

image.shape
```
### Crop a 300x300 region starting from (50, 50)
```
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```
### Convert BGR to RGB for displaying with Matplotlib
```
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
### Display the cropped region (ROI)
```
plt.imshow(roi_rgb)

plt.title("Cropped Region of Interest (ROI)")

plt.axis("off")

plt.show()
```

### 7.Flip the original image horizontal,vertical and display it.
### Load the image
```

image = cv2.imread('photo 3.jpeg')
```

### Flip the image horizontally (left-right)
```
flipped_horizontally = cv2.flip(image, 1)
```
### Convert BGR to RGB for displaying with Matplotlib
```
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```

### Horizontal flip
```
plt.imshow(flipped_horizontally_rgb)

plt.title("Flipped Horizontally")

plt.axis("off")
```
### Flip the image vertically (up-down)
```
flipped_vertically = cv2.flip(image, 0)
```
### Convert BGR to RGB for displaying with Matplotlib
```
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
### Vertical flip
```
plt.imshow(flipped_vertically_rgb)

plt.title("Flipped Vertically")

plt.axis("off")
```

## Output:

<img width="394" height="507" alt="Screenshot 2026-10-31 132958" src="https://github.com/user-attachments/assets/82b8fc15-7933-4d71-a463-b1ccc37cca73" />

<img width="363" height="527" alt="Screenshot 2026-10-31 133009" src="https://github.com/user-attachments/assets/fe54b474-8345-4ba0-b647-5368ddfd9d92" />

<img width="321" height="521" alt="Screenshot 2026-10-31 133018" src="https://github.com/user-attachments/assets/243c1ad5-3646-44c2-9dfe-67a071cf4f75" />

<img width="282" height="508" alt="Screenshot 2026-10-31 133028" src="https://github.com/user-attachments/assets/ad9234d1-9392-498b-9284-7c81b08f6a11" />

<img width="308" height="533" alt="Screenshot 2026-10-31 133035" src="https://github.com/user-attachments/assets/4a5f0625-7e30-4f97-8b1d-948358de3d44" />

<img width="289" height="522" alt="Screenshot 2026-10-31 133115" src="https://github.com/user-attachments/assets/59c44055-0b52-4bcd-8cb0-f74bd312ae27" />

<img width="382" height="521" alt="Screenshot 2026-10-31 133205" src="https://github.com/user-attachments/assets/21a0b4c2-484d-4707-a6cd-a47286b318d3" />

<img width="265" height="502" alt="Screenshot 2026-10-31 133215" src="https://github.com/user-attachments/assets/ad584a9c-189b-4860-9770-5f579e2f77fb" />

<img width="334" height="527" alt="Screenshot 2026-10-31 133228" src="https://github.com/user-attachments/assets/8472d043-fb4e-428a-8135-83f100a82e96" />

<img width="341" height="506" alt="Screenshot 2026-10-31 133244" src="https://github.com/user-attachments/assets/218ebe2d-72f3-4857-9da1-5be8c56147a1" />

<img width="455" height="516" alt="Screenshot 2026-10-31 133252" src="https://github.com/user-attachments/assets/2eee0fbe-9917-4903-b1b0-29d1d4e1e497" />

<img width="656" height="523" alt="Screenshot 2026-10-31 133259" src="https://github.com/user-attachments/assets/a979dda5-3f0e-4ebb-b40e-d5cda76bb341" />

<img width="361" height="515" alt="Screenshot 2026-10-31 133312" src="https://github.com/user-attachments/assets/2ca2897c-ace0-4221-8e31-264bd10cd562" />

<img width="330" height="507" alt="Screenshot 2026-10-31 133319" src="https://github.com/user-attachments/assets/2bbf958b-dcd0-41fd-ac48-c7a6b06e6c3d" />

## Result:

Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

