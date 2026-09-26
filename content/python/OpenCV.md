# 

## What is OpenCV?

OpenCV stands for **Open Source Computer Vision Library**.

It is a computer-vision library used to work with:

- Images
    
- Videos
    
- Camera input
    
- Pixels
    
- Image processing
    
- Object detection
    
- Computer-vision algorithms
    

In simple words:

> **OpenCV is a toolbox that allows a program to work with visual data.**

---

# How OpenCV Works

A computer does not understand an image like a human.

It represents an image as **pixels and numerical values**.

The basic flow is:

```text
Image / Camera
      ↓
    Pixels
      ↓
 Numerical Data
      ↓
 OpenCV Algorithms
      ↓
 Processed Result
```

For video:

```text
Camera
   ↓
Video Frames
   ↓
OpenCV
   ↓
Image Processing
   ↓
Result
```

---

# OpenCV Internally

OpenCV is mainly implemented in **C/C++**, while Python provides an interface to use OpenCV functionality.

Conceptually:

```text
Python Code
     ↓
OpenCV Python Interface
     ↓
OpenCV C/C++ Implementation
     ↓
Computer Processes Image Data
     ↓
Result
```

For example:

```python
import cv2

img = cv2.imread("photo.jpg")
```

Python calls the OpenCV functionality, and OpenCV loads and decodes the image into memory.

---

# Images and Pixels

An image is made up of many small elements called **pixels**.

A pixel is the smallest individual element of a digital image.

For a grayscale image, a pixel normally has an intensity value:

```text
0   → Black
255 → White
```

Values between them represent different shades of gray.

Example:

```text
0
50
128
200
255
```

---

# Color Images

A color image normally contains multiple channels.

OpenCV commonly uses:

```text
B → Blue
G → Green
R → Red
```

This is called **BGR**.

A pixel can therefore contain:

```text
[B, G, R]
```

Example:

```text
[255, 0, 0]
```

represents blue in OpenCV's BGR representation.

---

# Image as a NumPy Array

When an image is loaded using OpenCV, it is represented in Python as a NumPy array.

```python
img = cv2.imread("photo.jpg")
```

You can check:

```python
print(type(img))
```

The result is generally:

```text
numpy.ndarray
```

Therefore:

```text
Image
 ↓
Pixels
 ↓
Numbers
 ↓
NumPy Array
```

---

# Image Shape

We can use:

```python
print(img.shape)
```

For example:

```text
(720, 1280, 3)
```

This means:

```text
720  → Height
1280 → Width
3    → Color channels
```

The NumPy shape follows:

```text
(height, width, channels)
```

---

# Reading an Image

OpenCV provides:

```python
cv2.imread()
```

Example:

```python
import cv2

img = cv2.imread("photo.jpg")
```

Flow:

```text
photo.jpg
    ↓
cv2.imread()
    ↓
Image data in memory
    ↓
NumPy array
```

---

# Displaying an Image

Use:

```python
cv2.imshow("Image", img)
```

A complete example:

```python
import cv2

img = cv2.imread("photo.jpg")

cv2.imshow("Image", img)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Functions

`cv2.imread()` → reads an image

`cv2.imshow()` → displays an image

`cv2.waitKey()` → waits for a keyboard event

`cv2.destroyAllWindows()` → closes OpenCV windows

---

# Saving an Image

Use:

```python
cv2.imwrite("output.jpg", img)
```

Flow:

```text
OpenCV Image
     ↓
cv2.imwrite()
     ↓
output.jpg
```

---

# Accessing Pixels

An image is represented as an array, so individual pixels can be accessed.

```python
pixel = img[100, 200]
```

The indexing is:

```text
img[y, x]
```

So:

```python
img[100, 200]
```

means:

```text
y = 100
x = 200
```

For a BGR image, the returned value contains:

```text
[B, G, R]
```

---

# Grayscale

A color image can be converted into grayscale using:

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
```

Flow:

```text
BGR Image
    ↓
cv2.cvtColor()
    ↓
Grayscale Image
```

A color image has multiple channels, while a grayscale image has one intensity channel.

Grayscale is useful for many computer-vision operations because it reduces the amount of data that needs to be processed.

---

# Basic OpenCV Operations

OpenCV provides many operations for working with images.

## Resize

```python
cv2.resize()
```

Changes the dimensions of an image.

## Rotate

```python
cv2.rotate()
```

Rotates an image.

## Flip

```python
cv2.flip()
```

Flips an image.

## Crop

Cropping can be performed using NumPy slicing:

```python
crop = img[y1:y2, x1:x2]
```

---

# Drawing

OpenCV can draw directly on images.

Common functions:

```python
cv2.line()
cv2.rectangle()
cv2.circle()
cv2.putText()
```

These are useful for displaying:

- Bounding boxes
    
- Labels
    
- Points
    
- Detection areas
    
- Landmarks
    

---

# Image Processing

OpenCV provides algorithms for processing images.

Some important operations are:

```text
Blur
 ↓
Noise reduction

Thresholding
 ↓
Separate regions based on intensity

Edge Detection
 ↓
Find boundaries

Contours
 ↓
Find object boundaries
```

---

# Edge Detection

One commonly used OpenCV function is:

```python
cv2.Canny()
```

Conceptually:

```text
Original Image
      ↓
   Grayscale
      ↓
Noise Reduction
      ↓
Intensity Changes
      ↓
Edge Detection
      ↓
Edges
```

An edge is generally associated with a significant change in image intensity.

---

# Contours

Contours represent boundaries of objects or regions.

Common functions:

```python
cv2.findContours()
cv2.drawContours()
```

Conceptually:

```text
Object
  ↓
Boundary
  ↓
Contour
```

Contours can be useful for shape analysis and object detection tasks.

---

# Video Processing

OpenCV can work with camera/video input using:

```python
cv2.VideoCapture()
```

Example:

```python
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    if not ret:
        break

    cv2.imshow("Camera", frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

---

# How Webcam Processing Works

```text
Camera
   ↓
Frame 1
   ↓
OpenCV
   ↓
Process
   ↓
Display

Camera
   ↓
Frame 2
   ↓
OpenCV
   ↓
Process
   ↓
Display

Camera
   ↓
Frame 3
   ↓
OpenCV
   ↓
Process
   ↓
Display
```

This happens repeatedly, creating the appearance of real-time video.

---

# OpenCV in My Hand Controlled Game

OpenCV is used as the **visual input and processing layer**.

The complete system is:

```text
Camera
   ↓
OpenCV
   ↓
Video Frame
   ↓
MediaPipe
   ↓
Hand Detection
   ↓
Hand Landmarks
   ↓
Python Logic
   ↓
Game Action
```

### Roles

```text
OpenCV
→ Captures and processes camera frames

MediaPipe
→ Detects and tracks hand landmarks

Python
→ Applies application/game logic

Game
→ Performs the resulting action
```

---

# OpenCV vs MediaPipe

|OpenCV|MediaPipe|
|---|---|
|Computer-vision library|Framework/library with ready-made vision solutions|
|Works with images and video|Performs tasks such as hand tracking|
|Captures camera frames|Analyzes frames for supported tasks|
|Image processing|Hand/face/pose-related analysis|
|Provides algorithms and tools|Provides higher-level vision solutions|

Simple memory:

> **OpenCV = Works with the visual data**

> **MediaPipe = Understands specific visual tasks such as hand tracking**

---

# Important Functions

|Function|Purpose|
|---|---|
|`cv2.imread()`|Read image|
|`cv2.imshow()`|Display image|
|`cv2.waitKey()`|Wait for keyboard input|
|`cv2.destroyAllWindows()`|Close OpenCV windows|
|`cv2.imwrite()`|Save image|
|`cv2.cvtColor()`|Convert color spaces|
|`cv2.resize()`|Resize image|
|`cv2.rotate()`|Rotate image|
|`cv2.flip()`|Flip image|
|`cv2.VideoCapture()`|Capture video/camera|
|`cv2.Canny()`|Edge detection|
|`cv2.findContours()`|Find contours|
|`cv2.rectangle()`|Draw rectangle|
|`cv2.circle()`|Draw circle|
|`cv2.putText()`|Add text|

---

# Core Mental Model

Remember this:

```text
REAL WORLD
    ↓
Camera / Image
    ↓
Pixels
    ↓
Numbers
    ↓
NumPy Array
    ↓
OpenCV
    ↓
Computer-Vision Processing
    ↓
Useful Information / Modified Image
    ↓
Application
```

## Easy Memory Trick

> **Camera = Eyes 📷**

> **OpenCV = Vision Toolbox 👁️**

> **MediaPipe = Specialized Vision 🖐️**

> **Python = Logic 🧠**

> **Application = Action 🎮**