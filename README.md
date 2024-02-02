# Facial Morphing Project 🧒🔄🧑

## Overview
This project presents a sophisticated algorithm for creating a smooth transition between two portrait photos, for example, morphing one person's face into another. The transformation is achieved by warping and blending the pixels of the start and end images. 

This project is a complex blend of image processing techniques, primarily focusing on image warping and blending to achieve a morphing effect. The use of facial landmarks and triangulation ensures that the morphing looks natural and smooth.


```python
import cv2
from matplotlib import pyplot as plt
import numpy as np
import scipy
from PIL import Image

# Load, process, and display images...
# Landmark detection and processing...
# Triangulation and affine transformations...
# Blending and output...
```


## Features
- **Input**: Two portrait photos.
- **Output**: A series of "in-between" images creating a smooth transition from the start to the end image.
- **Technique**: Utilizes a parameter `w` varying from 0 to 1 for blending and warping images.
- **Efficiency**: Main loops for the affine warp part complete in 17-18 minutes, with instant blending.

## Process 🔄
1. **Landmark Detection**: Using Dlib for detecting facial landmarks.
2. **Triangulation**: Implements Delaunay Triangulation for mapping points.
3. **Intermediate Image Coordinates**: Calculates coordinates for "in-between" images.
4. **Affine Warp Estimation**: Estimates affine transformation for each triangle.
5. **Blending**: Applies blending using parameter `w`.
6. **Video Creation**: Generates a video of the transition using ffmpeg.

## Dependencies 📦
- OpenCV (cv2)
- Matplotlib
- NumPy
- SciPy
- Dlib (optional for automated landmark detection)

## Usage

### 1. **Setup and Image Importing**
   - Importing necessary libraries like `cv2`, `matplotlib`, `numpy`, etc.
   - Reading two images (`head1` and `head2`) using OpenCV and converting them to RGB format.
   - Cropping and resizing the images to ensure they are of the same dimensions.

### 2. **Landmark Detection**
   - Using `dlib`'s facial landmark detector to find key facial points (like eyes, nose, mouth corners) on both images.
   - Additional corner and edge center points are added to the detected landmarks for better mapping.
   - The landmarks are displayed side by side for visual verification.

### 3. **Triangulation**
   - Applying Delaunay Triangulation to the landmarks of each image.
   - This creates a mesh of triangles over the facial features, helping in detailed mapping and warping.
   - The triangulation of each image is visualized to ensure correct mapping.

### 4. **Intermediate Image Coordinates Calculation**
   - A function (`get_inbetween_cords`) calculates intermediate coordinates for all vertices of all triangles, creating "in-between" frames for the transition.
   - This step is crucial for creating a smooth morphing effect.

### 5. **Affine Warp Estimation and Application**
   - For every pair of corresponding triangles, the code estimates an Affine transform.
   - This transform is then applied to warp the images. The warping brings corresponding features (like eyes, nose, mouth) into alignment.
   - The warping process is done in two main loops, one for each direction of the morph (image1 to image2, and vice versa).

### 6. **Blending Images**
   - After warping, the images are blended together using the parameter `w`.
   - The blending is linear, controlled by `w`, which varies between 0 and 1 across the transition.
   - The blended images are stored in an array for later use.

### 7. **Generating and Viewing Output**
   - The morphed images are displayed using `matplotlib` to preview the output at different stages of the transition.
   - This step is more for debugging and visual confirmation of the process.

### 8. **Video Conversion**
   - Finally, the sequence of morphed images is compiled into a video using `ffmpeg`.
   - This showcases the smooth transition from the start image to the end image.

### Structure Summary:
- **Import and Prepare Data**: Images are loaded, processed, and landmarks are detected.
- **Triangulation**: The faces are broken down into triangular regions for detailed mapping.
- **Warping and Blending**: Through a series of steps, the images are warped and blended to create intermediate frames.
- **Output Generation**: The frames are compiled into a video to visualize the morphing effect.

### Additional Notes:
- **Affine Transformation**: A key part of this project. It's the mathematical process of transforming images so that triangles in one image map to corresponding triangles in another.
- **Manual vs. Automatic Landmark Detection**: While `dlib` is used for automated detection, there is an option to manually adjust or add landmarks for better accuracy.



## Converting Output to Video 🎥
The script utilizes `ffmpeg` to convert the sequence of images into a smooth transition video.

## Contact

Project Link: [https://github.com/kircova/Face-Morphing](https://github.com/kircova/Face-Morphing)

---
