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
```


## References

1. [Stanford CS131 Notes on Image Processing](http://vision.stanford.edu/teaching/cs131_fall1718/files/06_notes.pdf)
2. [Wikipedia - Canny Edge Detector](https://en.wikipedia.org/wiki/Canny_edge_detector)
3. Gonzalez, R. C., & Woods, R. E. (2002). *Digital Image Processing* (2nd ed.). Prentice Hall. [Google Books link](https://books.google.co.in/books?hl=en&lr=&id=a62xQ2r_f8wC&oi=fnd&pg=PA19&dq=digital+image+processing&ots=3B1yO1nE1D&sig=UPA_8QAuKPbJpSHDKw84BniVGFs&redir_esc=y#v=onepage&q=digital%20image%20processing&f=false)
4. [OpenCV Documentation: Feature Detection](https://docs.opencv.org/4.x/dd/d1a/group__imgproc__feature.html#ga04723e007ed888ddf11d9ba04e2232de)

