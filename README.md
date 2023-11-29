# Facial Morphing Project 🧑🔄👩

-------------
<img src='output.gif' width='300'>

## Overview
This project presents a sophisticated algorithm for creating a smooth transition between two portrait photos, for example, morphing one person's face into another. The transformation is achieved by warping and blending the pixels of the start and end images. 

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

## Converting Output to Video 🎥
The script utilizes `ffmpeg` to convert the sequence of images into a smooth transition video.

## Contact

Project Link: [https://github.com/kircova/Face-Morphing](https://github.com/kircova/Face-Morphing)

---
