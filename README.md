# Real-Time-Road-Lane-Detection



![Lane Detection GIF](ezgif-4-2f068c7bc5.gif)

This repository hosts a comprehensive collection of code and resources to empower developers, researchers, and enthusiasts in implementing robust lane detection systems. 
# Lane Detection

This repository contains a Python implementation of a lane detection system using image processing techniques. The primary goal of this project is to identify and track lanes on roadways, which is essential for applications such as autonomous vehicles and advanced driver assistance systems (ADAS).

## Overview

The main implementation consists of a Python script that utilizes the OpenCV library for video processing and computer vision tasks. Let's break down the key components of the code.

## BGR to RGB Conversion
```python
def bgr_rgb(image):
    rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
    return rgb
```
This function converts the color space of the input image from BGR (Blue-Green-Red) to RGB (Red-Green-Blue). This conversion is necessary for correct color representation when using matplotlib for visualization.


## Region of Interest
```python
def region_of_interest(image_height, image_width, xsize, ysize):
    # Definition of region of interest polygon
    # ...
    return region_thresholds
```
The region_of_interest function defines a polygonal region of interest in the image. This region is later used to mask out areas outside of the region, focusing the lane detection on the relevant part of the image.


## Colour Threshold Calculation
```python
def c_thresh(image):
    # Definition of color selection criteria
    # ...
    return color_thresholds
```
The c_thresh function establishes color selection criteria, creating a binary image based on whether pixels meet the specified color thresholds. This binary image helps identify lane markings.



## Image Processing Function
```python
def process_image(image):
    # ...
    return combo_image
```
The process_image function combines the previously defined functions to process each frame of the input video. It performs BGR to RGB conversion, applies color and region thresholding, and overlays the detected lanes on the original image.


## Main Implementation
```python
cap = cv2.VideoCapture('solidWhiteRight.mp4')
if not cap.isOpened():
    print("Error: Could not open video.")
    exit()

while cap.isOpened():
    ret, image = cap.read()

    if not ret:
        print("Completed !")
        break

    # Process the image
    result = process_image(image)

    # Display the processed image
    cv2.imshow('image', result)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```
The main implementation reads frames from a video file (solidWhiteRight.mp4), processes each frame using the process_image function, and displays the result in real-time. The processed video is shown, and the user can exit the display window by pressing 'q'.


# Running the Code
To run the lane detection code, make sure you have the required dependencies installed. You can install them using:

```bash
pip install opencv-python matplotlib numpy
```
After installing the dependencies, run the script using:
```bash
python lane_detection.py
```
Feel free to explore and modify the code to suit your specific needs or integrate it into your own projects. If you encounter any issues or have suggestions for improvements, feel free to contribute or open an issue. Happy coding!

Make sure to have all the dependencies installed and all the test image and video files before you run the code!
