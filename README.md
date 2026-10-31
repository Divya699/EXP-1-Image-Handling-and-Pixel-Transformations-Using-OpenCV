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
```

import cv2

import matplotlib.pyplot as plt
```

### Read the image using OpenCV
```

img = cv2.imread('pavithra image.png', cv2.IMREAD_COLOR)
```

### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
 ```

### Display the image using Matplotlib
```
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images

plt.title("Original Image")

plt.axis('off')

plt.show()
```

### 1.Draw a line from the top-left to the bottom-right of the image

### Load the image
```

image = cv2.imread('pavithra image.png')

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

image = cv2.imread('pavithra image.png') 
```

### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(255,255,0),10) # cv2.circle(image, center, radius, color, thickness)

plt.imshow(circle_img, cmap='viridis')

plt.title("Image with Circle")

plt.axis('off')

plt.show()
```
### 3.Draw a rectangle around  the whole image
### Load the image
```
image = cv2.imread('pavithra image.png')
```

### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape
```
### Draw a rectangle around the Whole image
```

rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 255, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')

plt.title("Image with Rectangle")

plt.axis('off')

plt.show()
```

### 4.Add the text "OpenCV Drawing" at the top-left corner of the image.
### Load the image
```
image = cv2.imread('pavithra image.png')

### Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

### Add text to the image
```

text_img = cv2.putText(img_rgb, "OpenCV Drawing", (50,100), cv2.FONT_HERSHEY_SIMPLEX, 3, (0, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')

plt.title("IMAGE WITH TEXT")

plt.axis('off')

plt.show()
```

### 5.Convert the image from RGB to HSV,GRAY,YCrCb,RGB
### Load the image
```

image = cv2.imread('pavithra image.png')
      
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
image = cv2.imread('pavithra image.png')

image.shape
```

### Resize the image to half its size
```

resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
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
image = cv2.imread('pavithra image.png')

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

image = cv2.imread('pavithra image.png')
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
