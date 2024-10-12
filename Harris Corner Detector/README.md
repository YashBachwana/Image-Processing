# Harris Corner Detection

This repository implements the **Harris Corner Detection** algorithm for identifying distinctive corners in an image. Corners are crucial features in computer vision tasks such as image matching, object recognition, and motion tracking.

## Background

Corners are regions in an image where intensity varies significantly in all directions. Unlike flat regions or edges, corners can be robustly identified through gradient analysis. The **Harris Corner Detection** method analyzes the sum of squared differences (SSD) between a patch and its shifted version:

$$
F(x, y) = \sum_{s,t} w(s,t) \left[ I(s+x, t+y) - I(s,t) \right]^2
$$

By expanding the intensity differences using a Taylor series and simplifying, we obtain the matrix form:

$$
F(x, y) = \begin{bmatrix} x & y \end{bmatrix} M \begin{bmatrix} x \\ y \end{bmatrix}
$$

where the gradient covariance matrix **M** is:

$$
M = \sum_{s,t} w(s,t) \begin{pmatrix} I_x^2 & I_x I_y \\ I_x I_y & I_y^2 \end{pmatrix}
$$

### Eigenvalue Analysis

The eigenvalues of **M** classify the nature of the region:
- **Flat Region:** $\lambda_1 \approx \lambda_2 \approx 0$
- **Edge:** One eigenvalue is large, the other is small.
- **Corner:** Both eigenvalues are large.

The **corner response function** is defined as:

$$
R = \det(M) - k \cdot \text{trace}(M)^2
$$

Here, **R** is positive for corners, negative for edges, and near zero for flat regions. The constant $k$ (typically $0 < k < 0.25$) adjusts the sensitivity of the detector.

## How It Works

The algorithm processes the image as follows:
1. **Compute Image Gradients**: Calculate gradients $I_x$ and $I_y$ using Sobel operators.
2. **Construct Gradient Covariance Matrix**: For each pixel, compute $I_x^2$, $I_y^2$, and $I_x I_y$, then apply a Gaussian filter to these values.
3. **Calculate Corner Response**: Use the Harris response function $R$ to evaluate each pixel.
4. **Thresholding and Non-Maximum Suppression**: Identify corners by thresholding $R$ and applying non-maximum suppression to retain only the strongest corners.

## Usage

### Requirements
- Python 3.x
- OpenCV
- NumPy
- Matplotlib

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/harris-corner-detection.git
   cd harris-corner-detection

## References

1. [Wikipedia - Harris Corner Detector](https://en.wikipedia.org/wiki/Harris_corner_detector)
2. [OpenCV Documentation: Harris Corner Detection](https://docs.opencv.org/4.x/dc/d0d/tutorial_py_features_harris.html)
3. [Medium - Harris Corner and Edge Detector](https://medium.com/@itberrios6/harris-corner-and-edge-detector-4169312aa2f8)
4. [Medium - Local Feature Descriptors: Harris and Hessian Corner Detector](https://medium.com/jun94-devpblog/cv-10-local-feature-descriptors-harris-and-hessian-corner-detector-7d524888abfd)
5. [Gonzalez, R. C., & Woods, R. E. (2002). *Digital Image Processing* (2nd ed.). Prentice Hall.](https://books.google.co.in/books?hl=en&lr=&id=a62xQ2r_f8wC&oi=fnd&pg=PA19&dq=digital+image+processing&ots=3B1yO1nE1D&sig=UPA_8QAuKPbJpSHDKw84BniVGFs&redir_esc=y#v=onepage&q=digital%20image%20processing&f=false)
