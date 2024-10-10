# Canny Edge Detector

## Overview
This project implements a **Canny Edge Detector**, a popular edge detection algorithm used in image processing to identify sharp changes in intensity, which signify edges in an image. The project also demonstrates edge detection fundamentals using first and second-order derivatives like Sobel and Laplacian operators, as well as the Prewitt kernel.

## Background
Edge detection is critical in computer vision, providing essential information for understanding the structure within an image. The Canny Edge Detector uses derivatives to identify points where the intensity changes abruptly, indicating potential edges.

### Derivatives in Edge Detection
Abrupt changes in intensity can be identified using derivatives. In this project, we compute first-order and second-order derivatives to highlight edges.

#### First-Order Derivatives
- **Sobel Operator**: Detects gradients (changes in intensity) in the x and y directions.
- **Prewitt Operator**: Similar to Sobel but with simpler kernels.

#### Second-Order Derivatives
- **Laplacian Operator**: Detects fine details by highlighting areas where intensity changes rapidly.

### Gradient Magnitude and Direction
The **gradient magnitude** measures the rate of intensity change, while the **gradient direction** points in the direction of the most significant change.

## Canny Edge Detection Pipeline

1. **Noise Reduction**: The image is smoothed using a Gaussian filter to reduce noise, which could otherwise be mistaken for edges.
2. **Gradient Calculation**: The gradient magnitude and direction are calculated using Sobel operators.
3. **Non-Maximum Suppression**: Thin the edges by removing pixels that are not part of the local maxima in the gradient direction.
4. **Double Thresholding**: Classify edges based on high and low thresholds to filter weak edges.
5. **Edge Tracking by Hysteresis**: Finalize edge detection by retaining strong edges and connecting weak edges that are adjacent to strong edges.

## Installation
To run the Canny Edge Detector, you'll need to install the following libraries:
```bash
pip install numpy opencv-python matplotlib seaborn scipy
