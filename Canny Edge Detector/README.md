# Canny Edge Detector

## Overview
This project implements a **Canny Edge Detector**, a popular edge detection algorithm used in image processing to identify sharp changes in intensity, which signify edges in an image. 

## Canny Edge Detection Pipeline

1. **Noise Reduction**: The image is smoothed using a Gaussian filter to reduce noise, which could otherwise be mistaken for edges.
2. **Gradient Calculation**: The gradient magnitude and direction are calculated using Sobel operators.
3. **Non-Maximum Suppression**: Thin the edges by removing pixels that are not part of the local maxima in the gradient direction.
4. **Double Thresholding**: Classify edges based on high and low thresholds to filter weak edges.
5. **Edge Tracking by Hysteresis**: Finalize edge detection by retaining strong edges and connecting weak edges that are adjacent to strong edges using Depth First Search.

## Installation
To run the Canny Edge Detector, you'll need to install the following libraries:
```bash
pip install numpy opencv-python matplotlib seaborn scipy
