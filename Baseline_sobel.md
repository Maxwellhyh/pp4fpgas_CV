# Introduction to Sobel edge detector

The Sobel operator, sometimes called the Sobel–Feldman operator or Sobel filter, is used in image processing and computer vision, particularly within edge detection algorithms where it creates an image emphasising edges. It is named after Irwin Sobel and Gary Feldman, colleagues at the Stanford Artificial Intelligence Laboratory (SAIL). Sobel and Feldman presented the idea of an "Isotropic 3 × 3 Image Gradient Operator" at a talk at SAIL in 1968. Technically, it is a discrete differentiation operator, computing an approximation of the gradient of the image intensity function. At each point in the image, the result of the Sobel–Feldman operator is either the corresponding gradient vector or the norm of this vector. The Sobel–Feldman operator is based on convolving the image with a small, separable, and integer-valued filter in the horizontal and vertical directions and is therefore relatively inexpensive in terms of computations. On the other hand, the gradient approximation that it produces is relatively crude, in particular for high-frequency variations in the image.

# Process

The operator uses two 3×3 kernels which are convolved with the original image to calculate approximations of the derivatives – one for horizontal changes, and one for vertical. If we define A as the source image, and Gx and Gy are two images which at each point contain the horizontal and vertical derivative approximations respectively, the computations are as follows:

<div align="center">
    <img src="https://render.githubusercontent.com/render/math?math=\huge%20I_x=\begin{bmatrix}-1%260%26%2B1\\-2%260%26%2B2\\-1%260%26%2B1\end{bmatrix},">
    <img src="https://render.githubusercontent.com/render/math?math=\huge%20I_y=\begin{bmatrix}-1%26-2%26-1\\0%260%260\\%2B1%26%2B2%26%2B1\end{bmatrix}">
    </div>

The x-coordinate is defined here as increasing in the "right"-direction, and the y-coordinate is defined as increasing in the "down"-direction. At each point in the image, the resulting gradient approximations can be combined to give the gradient magnitude, using:

<div align="center">
    <img src="https://render.githubusercontent.com/render/math?math=\huge%20G=\sqrt{G_x^2%2BG_y^2}">
</div>

Using this information, we can also calculate the gradient's direction:

<div align="center">
    <img src="https://render.githubusercontent.com/render/math?math=\huge%20a=arctan{\frac{G_y}{G_x}}">
</div>

where, for example, {\displaystyle \mathbf {\Theta } }{\displaystyle \mathbf {\Theta } } is 0 for a vertical edge which is lighter on the right side.

# Templete

# Boundary condition
